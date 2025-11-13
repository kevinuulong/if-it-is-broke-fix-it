<script>
	import favicon from '$lib/assets/favicon.svg';
	import homeIcon from '$lib/icons/Home.svg';
	import missingIcon from '$lib/icons/Warning.svg';
	import upcomingIcon from '$lib/icons/EventUpcoming.svg';
	import calendarIcon from '$lib/icons/CalendarCheck.svg';
	import addOnIcon from '$lib/icons/CalendarAddOn.svg';
	import popupIcon from '$lib/icons/OpenInNew.svg'
	import rectangle from '$lib/icons/Rectangle 1.svg'

	import { page } from '$app/stores';
	import { goto,invalidateAll } from '$app/navigation';

	let { children } = $props();

	let buttons = [
		{id: '/', icon: homeIcon, label: 'Home', popup:false},
		{id: '/missing', icon: missingIcon, label: 'Misssing Classes', popup:false},
		{id: '/future', icon: upcomingIcon, label: 'Future Classes', popup:false},
		{id: '/completed', icon: calendarIcon, label: 'Completed Classes', popup:false},
		{id: 'planned', icon: addOnIcon, label: 'Planned Classes', popup:true}
	]

	function redirect(endpoint) {
		if ($page.url.pathname === endpoint) {
            invalidateAll();
        } else {
            goto(endpoint, { invalidateAll:true });
        }
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="red_box">
</div>

{@render children()}

<div class="container">
	<div class="menu">
		{#each buttons as b}
			{#if b.popup == true}
				<button class='menu_button'><img src="{b.icon}"> {b.label} <img src="{popupIcon}" style="margin-left: auto"></button>
			{:else}
				<button on:click={() => redirect(b.id)} class={$page.url.pathname === b.id ? 'current_button' : 'menu_button'}><img src="{b.icon}"> {b.label} <img src={$page.url.pathname === b.id ? rectangle : ''} style="margin-left: auto"></button>
			{/if}
		{/each}
	</div>

	<div class="main_screen">
	</div>
</div>
<style>
    .red_box{
		background: var(--Primary-UC-Red, #E00122);
		display:flex;
		width: 100%;
		height: 50px;
		align-items: center;
		align-self: stretch;
	}

	.container{
		display: flex;
		width:100%;
    	height:100vh;
	}

	.menu{
		background: var(--Secondary-Grey, #F3F3F3);
		display: 1;
		width: 300px;
		flex-direction: column;
	}

	.main_screen{
		display: 1;
		flex-direction: column;
	}

	.menu_button{
		display: flex;
		width: 300px;
		height: 68px;
		padding: 10px 20px;
		align-items: center;
		gap: 20px;
	}

	.current_button{
		background: rgba(255, 255, 255, 0.70);
		display: flex;
		width: 300px;
		height: 68px;
		padding: 10px 0 10px 20px;
		align-items: center;
		gap: 20px;
	}
</style>