<script module lang="ts">
  import type { Snippet } from "svelte";
  export type FieldType = {
    label: string;
    name: string;
    placeholder: string;
    required: boolean;
    field: Snippet<[FieldType]>;
    options?: { label: string; value: string }[];
  };

  export { TextInput, SelectInput };
</script>

{#snippet TextInput(field: FieldType)}
  <input
    id={field.name}
    class="input"
    name={field.name}
    placeholder={field.placeholder}
  />
{/snippet}

{#snippet SelectInput(field: FieldType)}
  <select class="select">
    <option disabled selected>{field.placeholder}</option>
    {#each field.options as opt}
      <option value={opt.value}>{opt.label}</option>
    {/each}
  </select>
{/snippet}
