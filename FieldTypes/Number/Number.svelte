<script>
  import Input from '../../Input.svelte'

  export let field
</script>

<div class="w-full">
  <Input 
    {...field} 
    bind:value={field.value}
    type="number"
  />
</div>

