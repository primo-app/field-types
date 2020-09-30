<script>
  import {createEventDispatcher} from 'svelte'
  const dispatch = createEventDispatcher()

  import marked from 'marked'
  export let field

  function parseContent(e) {
    const markdown = marked(e.target.value)
    field.value = markdown
    dispatch('input')
  }
</script>

<label class="label" for={field.id}>
  <span>{ field.label }</span>
  <textarea id={field.id} rows="8" on:input={parseContent}></textarea>
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