<script>
    import SideBarItem from "./SideBarItem.svelte";
    import { items } from "../../data/items";
</script>

<div class="sidebar">
    {#if window.electronAPI.isMac}
        <div class="macos-header" />
	{:else}
		<div class="winlinux-header" />
    {/if}
    {#each items as item, i}
        <SideBarItem data={item} {i} />
    {/each}
</div>

<style>
    .sidebar {
        background-color: transparent;
        backdrop-filter: blur(15px);
        user-select: none;
    }
    .macos-header {
        -webkit-app-region: drag;
        height: 50px;
        margin-bottom: 0px;
    }
	.winlinux-header {
		height: 7px;
		-webkit-app-region: drag;
	}
</style>
