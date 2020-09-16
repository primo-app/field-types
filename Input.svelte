<script lang="ts">
  import {createEventDispatcher} from 'svelte'
  const dispatch = createEventDispatcher()

  export let label
  export let value
  export let type = 'text'
  export let disabled = false
  export let variants = ''
  export let options = {}

  const passedOptions = {
    disabled: false,
    title: `${label} input field`,
    ...options
  }

  function onInput({target}) {
    const {value:inputValue} = target
    if (['text','number','range'].includes(type)) {
      value = inputValue
    } else {
      console.log('Value not saved:', inputValue, e)
    } 
    dispatch('input')
  }

</script>

<!-- svelte-ignore a11y-label-has-associated-control -->
<label class="flex flex-col text-xl font-medium {variants}">
  <span class="mb-2 text-sm">{ label }</span>
  <input 
    class="input"
    {value}
    {type}
    {disabled}
    {...options}
    on:input={onInput} 
  >
  <slot></slot>
</label>

<style>
  input {
    outline-color: rgb(248,68,73);
    @apply bg-white p-2 border-2 border-gray-100;
  }
</style>