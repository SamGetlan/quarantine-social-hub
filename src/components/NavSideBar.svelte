<script lang="typescript">
  import { MDCDrawer } from '@material/drawer';
  import { afterUpdate, onMount } from 'svelte';

  export let show = false;
  
  let navSideBar: MDCDrawer;
  let navSideBarElement: HTMLBaseElement;

  onMount(() => {
    navSideBar = MDCDrawer.attachTo(navSideBarElement);
  });

  $: if (navSideBar && navSideBar.open !== show) {
    navSideBar.open = show;
  }

</script>

<aside bind:this={navSideBarElement} class="mdc-drawer mdc-drawer--dismissible mdc-top-app-bar--fixed-adjust">
  <div class="mdc-drawer__content">
    <div class="mdc-list">
      <a class="mdc-list-item mdc-list-item--activated" href="#/" aria-current="page">
        <i class="material-icons mdc-list-item__graphic" aria-hidden="true">inbox</i>
        <span class="mdc-list-item__text">Inbox</span>
      </a>
      <a class="mdc-list-item" href="#/">
        <i class="material-icons mdc-list-item__graphic" aria-hidden="true">send</i>
        <span class="mdc-list-item__text">Outgoing</span>
      </a>
      <a class="mdc-list-item" href="#/">
        <i class="material-icons mdc-list-item__graphic" aria-hidden="true">drafts</i>
        <span class="mdc-list-item__text">Drafts</span>
      </a>
    </div>
  </div>
</aside>

<style lang="scss" global>
  @import '@material/top-app-bar/mdc-top-app-bar';
  @import '@material/drawer/mdc-drawer';
  @import '@material/list/mdc-list';
</style>