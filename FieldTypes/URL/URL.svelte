<script>
  import {TextField} from '@primo-app/ui'

  export let field
</script>

<div class="w-full">
  <TextField 
    {...field} 
    bind:value={field.value}
    type="url"
  />
</div>

