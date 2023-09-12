<script lang="ts">
  import DarkMode from 'svelte-dark-mode';
  import { afterUpdate, onMount } from "svelte";
  import SvgIcon from "$lib/components/general/SvgIcon.svelte";

  $: theme = ''

  afterUpdate(() => {
    document.body.className = theme
  });

  $: if (typeof window !== 'undefined')
    document.body.className = theme;

  $: switchTheme = theme === 'dark' ? 'light' : 'dark'

  onMount(() => loadItem())

  $: text = ''

  async function loadItem() {
    const res = await fetch('/icons/weather/sun.svg')
    text = await res.text()
  }
</script>

<DarkMode bind:theme />

<h1>This is {theme} mode.</h1>
<p>Change the theme and reload the page.</p>
<button on:click={() => (theme = switchTheme)}>
  Switch to {switchTheme} mode
</button>
<SvgIcon icon="weather/sun"></SvgIcon>
<i>
  {@html text}
</i>

<style>

</style>