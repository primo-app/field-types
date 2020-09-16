<script>
  import Input from '../../Input.svelte'

  export let field
</script>

<div class="w-full">
  <Input 
    label={field.label}
    bind:value={field.value}
    type="range"
    options={{
      list: 'tickmarks',
      step:'10'
    }}
  >
    <datalist id="tickmarks">
      <option value="0" label="0%"></option>
      <option value="10"></option>
      <option value="20"></option>
      <option value="30"></option>
      <option value="40"></option>
      <option value="50" label="50%"></option>
      <option value="60"></option>
      <option value="70"></option>
      <option value="80"></option>
      <option value="90"></option>
      <option value="100" label="100%"></option>
    </datalist>
  </Input>
</div>

