<script lang="typescript">
export let title = 'Title';
import { onMount } from 'svelte';
import { MDCTopAppBar } from '@material/top-app-bar';

onMount(() => {
  const topAppBarElement = document.querySelector('.mdc-top-app-bar');
  const topAppBar = new MDCTopAppBar(topAppBarElement);
})

</script>
  
<header class="mdc-top-app-bar">
  <div class="mdc-top-app-bar__row">
    <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
      <button class="material-icons mdc-top-app-bar__navigation-icon mdc-icon-button">menu</button>
      <span class="mdc-top-app-bar__title">{title}</span>
    </section>
  </div>
</header>

<style lang="scss">
  @import "@material/top-app-bar/mdc-top-app-bar";
  @import "@material/icon-button/mdc-icon-button";
</style>