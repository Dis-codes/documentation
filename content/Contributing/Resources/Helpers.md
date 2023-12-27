---
title: Helper
---

# Svelte
Framework [svelte](https://svelte.dev/) is used in our project, it supports fast deploys and is reactive. 
There is also a VSC [extension](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). 
Here's an example:
```html
{#if $user}
    <slot/>
{:else}
    <span class="loading loading-spinner text-discodes loading-lg"></span>
{/if}
```
# Tailwind
We use [tailwind](https://tailwindcss.com/) for our CSS framework, it´s not just easier, but also better. It uses class names. \
See class names directly in project [here](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) 
Hide class names when they are a lot of them with [this VSC extention](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) 

# DaisyUI
Is a Tailwind plugin used to make UI and DX better and faster. [DaisyUI](https://daisyui.com/) Has 53 navite components including buttons, modals, etc. 

# Supabase
[Supabase](https://supabase.com/) is an open source Firebase alternative. 
It is used as authentification provider for the discord oAuth2 and for database management using the SQL language.

# Vercel
We currently use [vercel](https://discodes.vercel.app/) as our website hosting. 
All branches, merges and commits will be automatically created a preview link by vercel. Preview links are used to visualize the changes made before pushing to main. 
**All commits or merges to the main branch will update the website.** 
