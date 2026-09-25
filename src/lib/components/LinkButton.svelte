<script lang="ts">
  import { fly } from 'svelte/transition';
  
  let { href, iconSrc, altText, brandClass, label, delay = 0 } = $props<{
    href: string;
    iconSrc?: string;
    altText?: string;
    brandClass: string;
    label: string;
    delay?: number;
  }>();
</script>

<a 
  class="button {brandClass}" 
  {href} 
  target="_blank" 
  rel="noopener noreferrer"
  in:fly={{ y: 20, duration: 600, delay }}
>
  {#if iconSrc}
    <img class="icon" aria-hidden="true" src={iconSrc} alt={altText} />
  {/if}
  {label}
</a>

<style>
  .button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 18.75rem; /* 300px */
    min-height: 3rem; /* 48px */
    padding: 0.75rem 1rem; /* 12px 16px */
    font-size: 1.125rem; /* 18px */
    font-weight: 700;
    font-family: "Space Mono", monospace;
    text-decoration: none;
    white-space: normal;
    background-color: var(--button-background, #232931);
    color: var(--button-text, #ffffff);
    border: var(--button-border, none);
    border-radius: 37px;
    cursor: pointer;
    box-sizing: border-box;
    transition: filter 0.2s ease, transform 0.2s ease, box-shadow 0.2s ease;
    margin-bottom: 1rem;
  }

  .button:hover {
    filter: brightness(90%);
    transform: translateY(-2px) scale(1.02);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  .icon {
    width: 1.5rem; /* 24px */
    height: 1.5rem; /* 24px */
    margin-right: 0.5rem; /* 8px */
    fill: currentColor;
  }
</style>
