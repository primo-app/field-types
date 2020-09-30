<script>
  import {createEventDispatcher} from 'svelte'
  const dispatch = createEventDispatcher()

  import marked from 'marked'
  export let field

  function parseContent() {
    const markdown = marked(unparsed)
    field.value = markdown
    dispatch('input')
  }

  let unparsed = field.value
</script>

<label class="label" for={field.id}>
  <span>{ field.label }</span>
  <textarea id={field.id} rows="8" bind:value={unparsed} on:input={parseContent}></textarea>
</label>

<style>
  .label {
    @apply flex flex-col mb-2 font-medium;

    span {
      @apply mb-2;
    }

    textarea {
      @apply p-2 border-2 border-gray-100;
      outline-color: rgb(248,68,73);
    }
  }
</style>