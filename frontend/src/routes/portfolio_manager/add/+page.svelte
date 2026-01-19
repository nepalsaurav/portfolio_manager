<script lang="ts">
  import type { FieldType } from "$lib/components/form/FormSnippet.svelte";
  import { TextInput, SelectInput } from "$lib/components/form/FormSnippet.svelte";
  let fields: FieldType[] = [
    {
      label: "PM Code",
      name: "pm_code",
      placeholder: "type pm code",
      required: true,
      field: TextInput,
    },
    {
      label: "Name",
      name: "name",
      placeholder: "portfolio manager full name",
      required: true,
      field: TextInput,
    },
    {
      label: "Gender",
      name: "gender",
      placeholder: "please select gender",
      required: true,
      options: [
        { label: "Male", value: "Male" },
        { label: "Female", value: "Female" },
      ],
      field: SelectInput,
    },
    {
      label: "Status",
      name: "status",
      placeholder: "please select status",
      required: true,
      options: [
        { label: "Active", value: "Active" },
        { label: "Inactive", value: "Inactive" },
      ],
      field: SelectInput,
    },
    {
      label: "Phone Number",
      name: "phone_number",
      placeholder: "enter phone number",
      required: false,
      field: TextInput,
    }
  ];
</script>

<div class="p-4">
    <div class="border p-6 border-zinc-300">
        <form>
          <fieldset>
            <legend class="font-bold mb-3">Add Protfolio Manager</legend>
            <div class="mb-4 flex flex-row-reverse gap-3">
                <button class="btn btn-secondary">Cancel</button>
                <button class="btn btn-primary">Save</button>
            </div>
            <div class="grid grid-cols-3 gap-6">
              {#each fields as field}
                <div class="flex gap-2 flex-col">
                  <label class="label" for={field.name}>{field.label}</label>
                  {@render field.field(field)}
                </div>
              {/each}
            </div>
          </fieldset>
        </form>
    </div>
</div>
