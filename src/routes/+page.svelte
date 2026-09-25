<script lang="ts">
  import ProfileHeader from '$lib/components/ProfileHeader.svelte';
  import LinkButton from '$lib/components/LinkButton.svelte';

  const links = [
    {
      href: 'https://www.instagram.com/cardcollectionstudio',
      iconSrc: '/images/icons/instagram.svg',
      altText: 'Instagram Logo',
      brandClass: 'button-instagram',
      label: 'Instagram'
    },
    {
      href: 'https://id.shp.ee/uSs9odoq',
      iconSrc: '/images/icons/shopee.png',
      altText: 'Shopee Logo',
      brandClass: 'button-shopee',
      label: 'Shopee (ID)'
    },
    {
      href: 'https://tk.tokopedia.com/ZSV5Sxf3J',
      iconSrc: '/images/icons/tokopedia.png',
      altText: 'Tokopedia Logo',
      brandClass: 'button-tokopedia',
      label: 'tokopedia (ID)'
    }
  ];
</script>

<svelte:head>
  <link rel="stylesheet" href="/css/reset.css" />
  <link rel="stylesheet" href="/css/brands.css" />
</svelte:head>

<div class="container">
  <main>
    <ProfileHeader />
    <nav class="button-stack" aria-label="Links">
      {#each links as link, index}
        <LinkButton {...link} delay={(index + 1) * 150} />
      {/each}
    </nav>
  </main>
</div>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    background-color: #ffffff;
    color: #232931;
    font-family: "Plus Jakarta Sans", system-ui, sans-serif;
    font-weight: 400;
    line-height: 1.6;
    display: flex;
    justify-content: center;
    min-height: 100vh;
  }

  @media (prefers-color-scheme: dark) {
    :global(body) {
      background-color: #121212;
      color: #ffffff;
    }
  }

  .container {
    width: 100%;
    max-width: 480px; /* Standard linktree width */
    margin: 0 auto;
    padding: 2rem 1rem;
    box-sizing: border-box;
  }

  main {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .button-stack {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
  }
</style>
