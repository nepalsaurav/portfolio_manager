<script lang="ts">
  import { page } from "$app/stores";
  type Menu = {
    label: string;
    url: string;
  };

  let menuItems: Menu[] = [
    {
      label: "Dashboard",
      url: "/",
    },
    {
      label: "Portfolio Manager",
      url: "/portfolio_manager",
    },
  ];
</script>

<header class="border-b border-zinc-300">
  <div class="flex gap-3">
    {#each menuItems as item}
      <a href={item.url} class="text-zinc-700 hover:bg-zinc-200 p-1"
        >{item.label}</a
      >
    {/each}
  </div>
</header>
