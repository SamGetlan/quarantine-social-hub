<script lang="typescript">
import { createEventDispatcher, onMount } from 'svelte';
import { MDCTopAppBar } from '@material/top-app-bar';

export let title = 'Title';

const dispatch = createEventDispatcher();
let topAppBar: MDCTopAppBar;
let topAppBarElement: HTMLBaseElement;

onMount(() => {
  topAppBar = new MDCTopAppBar(topAppBarElement);
  topAppBar.listen('MDCTopAppBar:nav', () => {
      dispatch('toggleNav');
		});
});

</script>
  
<header bind:this={topAppBarElement} class="mdc-top-app-bar app-bar">
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

  .mdc-top-app-bar {
	  z-index: 7;
  }
</style>