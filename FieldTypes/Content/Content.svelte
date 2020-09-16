<script>
  export let field
</script>

<label class="label" for={field.id}>
  <span>{ field.label }</span>
  <textarea id={field.id} rows="4" bind:value={field.value} on:input></textarea>
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