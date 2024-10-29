<script>
import { mode, toggleMode } from "mode-watcher";
import Button from "./ui/button/button.svelte";
import { Sun, Moon } from 'lucide-svelte';

</script>
<Button onclick={() => {toggleMode()}}>{#if $mode === 'dark'}
    <Sun />
  {:else}
    <Moon />
  {/if}</Button>