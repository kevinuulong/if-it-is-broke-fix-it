<script>
	import favicon from '$lib/assets/favicon.svg';
	import homeIcon from '$lib/icons/Home.svg';
	import missingIcon from '$lib/icons/Warning.svg';
	import upcomingIcon from '$lib/icons/EventUpcoming.svg';
	import calendarIcon from '$lib/icons/CalendarCheck.svg';
	import addOnIcon from '$lib/icons/CalendarAddOn.svg';
	import popupIcon from '$lib/icons/OpenInNew.svg'
	import rectangle from '$lib/icons/Rectangle 1.svg'
	import back from '$lib/icons/ArrowBack.svg'
	import history from '$lib/icons/History.svg'
	import favorite from '$lib/icons/Favorite.svg'

	import { page } from '$app/stores';
	import { goto,invalidateAll } from '$app/navigation';

	let { children } = $props();

	let buttons = [
		{id: '/', icon: homeIcon, label: 'Home', popup:false},
		{id: '/missing', icon: missingIcon, label: 'Missing Classes', popup:false},
		{id: '/future', icon: upcomingIcon, label: 'Future Classes', popup:false},
		{id: '/completed', icon: calendarIcon, label: 'Completed Classes', popup:false},
		{id: 'https://uc.collegescheduler.com/', icon: addOnIcon, label: 'Planned Classes', popup:true}
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
	<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
  		<path d="M7.825 13L13.425 18.6L12 20L4 12L12 4L13.425 5.4L7.825 11H20V13H7.825Z" fill="white"/>
	</svg>
	<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
  		<path d="M12 21C9.7 21 7.696 20.2377 5.988 18.713C4.28 17.1883 3.30067 15.284 3.05 13H5.1C5.33333 14.7333 6.10433 16.1667 7.413 17.3C8.72167 18.4333 10.2507 19 12 19C13.95 19 15.6043 18.321 16.963 16.963C18.3217 15.605 19.0007 13.9507 19 12C18.9993 10.0493 18.3203 8.39533 16.963 7.038C15.6057 5.68067 13.9513 5.00133 12 5C10.85 5 9.775 5.26667 8.775 5.8C7.775 6.33333 6.93333 7.06667 6.25 8H9V10H3V4H5V6.35C5.85 5.28333 6.88767 4.45833 8.113 3.875C9.33833 3.29167 10.634 3 12 3C13.25 3 14.421 3.23767 15.513 3.713C16.605 4.18833 17.555 4.82967 18.363 5.637C19.171 6.44433 19.8127 7.39433 20.288 8.487C20.7633 9.57967 21.0007 10.7507 21 12C20.9993 13.2493 20.762 14.4203 20.288 15.513C19.814 16.6057 19.1723 17.5557 18.363 18.363C17.5537 19.1703 16.6037 19.812 15.513 20.288C14.4223 20.764 13.2513 21.0013 12 21ZM14.8 16.2L11 12.4V7H13V11.6L16.2 14.8L14.8 16.2Z" fill="white"/>
	</svg>
	<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
  		<path d="M12 21L10.55 19.7C8.86667 18.1833 7.475 16.875 6.375 15.775C5.275 14.675 4.4 13.6873 3.75 12.812C3.1 11.9367 2.646 11.1327 2.388 10.4C2.13 9.66733 2.00067 8.91733 2 8.15C2 6.58333 2.525 5.275 3.575 4.225C4.625 3.175 5.93333 2.65 7.5 2.65C8.36667 2.65 9.19167 2.83333 9.975 3.2C10.7583 3.56667 11.4333 4.08333 12 4.75C12.5667 4.08333 13.2417 3.56667 14.025 3.2C14.8083 2.83333 15.6333 2.65 16.5 2.65C18.0667 2.65 19.375 3.175 20.425 4.225C21.475 5.275 22 6.58333 22 8.15C22 8.91667 21.871 9.66667 21.613 10.4C21.355 11.1333 20.9007 11.9373 20.25 12.812C19.5993 13.6867 18.7243 14.6743 17.625 15.775C16.5257 16.8757 15.134 18.184 13.45 19.7L12 21Z" fill="white"/>
	</svg>
	<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 48 48" fill="none" class="uc_logo">
  		<path d="M6 8V9.74657H9.13575V24.9648C9.13575 31.0621 13.11 34.2286 19.1598 34.3286C21.4732 36.9006 24.7475 38.6958 28.467 39.2261C28.7605 39.2695 29.0398 39.2995 29.2717 39.3198V37.5854C28.9727 37.5339 28.7649 37.4854 28.7649 37.4854C23.0651 36.0347 18.8621 31.1836 18.8621 24.9649C18.8621 20.2001 21.6479 16.3471 25.7626 14.1871V11.8458C19.8491 13.7824 15.6084 18.7821 15.6084 24.9651C15.6084 28.0226 16.4055 30.4116 17.7949 32.5511C14.1379 31.9086 12.5619 29.3576 12.5619 24.9651V8.0003H12.558H6.0005L6 8ZM23.2828 8.00928V9.75488H29.2668V8.00928H23.2828ZM31.2103 11.0498C30.5496 11.0498 29.8986 11.0884 29.2586 11.165L29.2713 24.9648C29.2713 27.6488 28.8838 29.2328 27.5101 30.9218C25.9988 29.2543 25.7601 27.3603 25.7601 24.9648C25.7601 23.6885 25.7621 17.6165 25.7621 17.6165C23.7565 19.5565 22.5023 21.9665 22.5023 24.9648C22.5023 31.2373 27.3458 36.1358 33.2568 36.1358C35.2853 36.1358 37.6253 35.6398 39.3326 34.4785L38.9019 33.8355C36.5975 35.0117 31.9197 35.2849 29.0617 32.6099C31.4782 30.8264 32.6969 28.5439 32.6969 24.9649V12.6881C36.7442 12.6881 39.1712 15.0954 39.3019 17.8541L40.8073 18.15L41.862 12.0085L40.0695 11.6599L39.8508 12.9705C36.618 11.3445 33.9055 11.0501 31.2105 11.0501L31.2103 11.0498Z" fill="white"/>
	</svg>
</div>

{@render children()}

<div class="container">
	<div class="menu">
		{#each buttons as b}
			{#if b.popup == true}
				<!--<button class='menu_button'><img src="{b.icon}" alt="icon"> {b.label} <img src="{popupIcon}" alt="popup" style="margin-left: auto"></button>-->
				<a href="{b.id}" target="_blank" class="menu_button">
					<img src="{b.icon}" alt="icon"> {b.label} <img src="{popupIcon}" alt="popup" style="display:flex; margin-left: auto">
				</a>
				
			{:else}
				<!--<button onclick={() => redirect(b.id)} class={$page.url.pathname === b.id ? 'current_button' : 'menu_button'}><img src="{b.icon}" alt="icon"> {b.label} <img src={$page.url.pathname === b.id ? rectangle : ''} alt="" style="margin-left: auto"></button>-->
				<a href="{b.id}" class={$page.url.pathname === b.id ? 'current_button' : 'menu_button'}>
					<img src="{b.icon}" alt="icon"> {b.label} <img src={$page.url.pathname === b.id ? rectangle : ''} alt="" style="display:flex; margin-left: auto">
				</a>
			{/if}
		{/each}
	</div>

	<div class="main_screen">
	</div>
</div>
<style>
    .red_box{
		background: var(--Primary-UC-Red, #E00122);
		display: flex;
		padding: 10px 20px;
		align-items: center;
		gap: 20px;
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
		width: 260px;
		height: 68px;
		padding: 10px 20px;
		align-items: center;
		gap: 20px;
		border: 0px;
		text-decoration: none;
		color: black;
	}
	.current_button{
		background: rgba(255, 255, 255, 0.70);
		display: flex;
		width: 280px;
		height: 68px;
		padding: 10px 0 10px 20px;
		align-items: center;
		gap: 20px;
		text-decoration: none;
		color: black;
	}
	.uc_logo{
		margin-left: auto
	}
</style>