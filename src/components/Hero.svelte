<script>
  import { siteInfo } from "../stores.js";
  import { getContext } from "svelte";
</script>

<style lang="scss">
  @import "../css/variables";
  @import "../css/mixins";

  .gh-head {
    position: relative;
    display: flex;
    width: 100%;
    font-size: 1.6rem;
    align-items: center;
    z-index: 1;
    box-sizing: border-box;
    a {
      color: inherit;
      text-decoration: none;
    }
  }
  .gh-head-brand {
    display: inline-block;
    margin: 0 auto;
    max-width: 300px;
    text-align: center;
    word-break: break-all;
    .logo {
      display: block;
      font-weight: 600;
      font-size: 2.2rem;
      line-height: 1.2em;
      img {
        max-height: 84px;
      }
    }
  }
</style>

<header id="gh-head" class="gh-head gh-container">
  <div class="gh-head-brand">
    <a class="logo" href={$siteInfo.url}>
      {#if $siteInfo.logo}
        <img src={$siteInfo.logo} alt={$siteInfo.title} />
      {:else}
        <span>{$siteInfo.title}</span>
      {/if}
    </a>
  </div>
</header>
