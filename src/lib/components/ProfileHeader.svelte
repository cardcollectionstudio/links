<script lang="ts">
  import { fade, slide } from 'svelte/transition';
</script>

<div class="header" in:fade={{ duration: 800 }}>
  <div class="avatars" in:slide={{ duration: 600, delay: 200 }}>
    <img class="avatar avatar--none" src="/images/ccs_black.svg" alt="Card Collection Studio" width="128" height="128">
  </div>
  <p in:fade={{ duration: 800, delay: 400 }}>Protect. Shuffle. Dominate.</p>
</div>

<style>
  .header {
    text-align: center;
    margin-bottom: 2rem;
  }
  
  .avatars {
    display: flex;
    justify-content: center;
  }

  .avatar {
    width: 8rem;
    height: 8rem;
    transition: transform 0.3s ease;
  }
  
  .avatar:hover {
    transform: scale(1.05);
  }

  @media (prefers-color-scheme: dark) {
    .avatar {
      filter: invert(1);
    }
    .avatar:hover {
      filter: invert(1) brightness(90%);
    }
  }

  p {
    margin: 1.5rem 0;
    font-size: 1.25rem;
    line-height: 1.6;
  }
</style>
