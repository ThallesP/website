<script lang="ts">
    import SunIcon from "@lucide/svelte/icons/sun";
    import MoonIcon from "@lucide/svelte/icons/moon";

    import { toggleMode, mode } from "mode-watcher";
    import { Button } from "$lib/components/ui/button/index.js";
</script>

<Button onclick={toggleMode} variant="outline" size="icon">
    {#if $mode === "dark"}
        <SunIcon />
    {:else}
        <MoonIcon />
    {/if}
</Button>
