<script lang="ts">
	import { goto } from "$app/navigation";

    export let menus: any = [];

    async function handleNav(route: string) {
        try {
            await goto(route);
        } catch (error) {
            console.error('Navigation failed! ', error);
        }
        console.log(`Navigating to ${route}`);
    }
</script>

<div class="navbar">
    <ul>
        {#each menus as menu, index}
            <li class={index === 0 ? "brand" : ""}>
                <button on:click={() => handleNav(menu.url)}>{menu.name}</button>
            </li>
        {/each}
    </ul>
</div>

<style>
    .navbar {
        width: 100vw;
        height: 40px;
        background-color: royalblue;
    }

    ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        height: 100%;
        display: flex;
        align-items: center;
    }
    
    li {
        font-size: 16px;
        color: white;
        cursor: pointer;
        transition: background-color 0.2s;
        padding: 0;
    }

    li button {
        background: none;
        border: none;
        color: white;
        padding: 11px 16px;
        font-size: 16px;
        cursor: pointer;
        width: 100%;
        height: 100%;
        transition: background-color 0.2s;
    }

    li button:hover {
        background-color: rgba(255, 255, 255, 0.1);
    }

    .brand {
        font-weight: bold;
        background-color: rgba(0, 0, 0, 0.1);
    }

    .brand:hover {
        background-color: rgba(0, 0, 0, 0.2);
    }
</style>