<script>
	import favicon from "$lib/assets/favicon.svg";
	import "../global.css";

	import homeIcon from "$lib/icons/Home.svg";
	import missingIcon from "$lib/icons/Warning.svg";
	import upcomingIcon from "$lib/icons/EventUpcoming.svg";
	import calendarIcon from "$lib/icons/CalendarCheck.svg";
	import addOnIcon from "$lib/icons/CalendarAddOn.svg";
	import popupIcon from "$lib/icons/OpenInNew.svg";
	import rectangle from "$lib/icons/Rectangle 1.svg";
	import back from "$lib/icons/ArrowBack.svg?raw";
	import history from "$lib/icons/History.svg?raw";
	import favorite from "$lib/icons/Favorite.svg?raw";

	import ProgressWidget from "$lib/ProgressWidget.svelte";

	import { page } from "$app/stores";
	import { browser } from "$app/environment";
	import { goto, invalidateAll } from "$app/navigation";
	import Button from "$lib/Button.svelte";

	let { children } = $props();
	let previousPath = "/";

	let buttons = [
		{ id: "/", icon: homeIcon, label: "Home", popup: false },
		{
			id: "/missing",
			icon: missingIcon,
			label: "Missing Classes",
			popup: false,
		},
		{
			id: "/future",
			icon: upcomingIcon,
			label: "Future Classes",
			popup: false,
		},
		{
			id: "/completed",
			icon: calendarIcon,
			label: "Completed Classes",
			popup: false,
		},
		{
			id: "https://uc.collegescheduler.com/",
			icon: addOnIcon,
			label: "Planned Classes",
			popup: true,
		},
	];

	/*function redirect(endpoint) {
		if ($page.url.pathname === endpoint) {
			invalidateAll();
		} else {
			previousPath = $page.url.pathname
			goto(endpoint, { invalidateAll: true });
		}
	}*/

	function goback(){
		window.history.back()
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="red_box">
	<Button icon={back} onclick={() => goback()}></Button>
	<Button icon={history}></Button>
	<Button icon={favorite}></Button>

	<svg
		xmlns="http://www.w3.org/2000/svg"
		width="48"
		height="48"
		viewBox="0 0 48 48"
		fill="none"
		class="uc_logo"
	>
		<path
			d="M6 8V9.74657H9.13575V24.9648C9.13575 31.0621 13.11 34.2286 19.1598 34.3286C21.4732 36.9006 24.7475 38.6958 28.467 39.2261C28.7605 39.2695 29.0398 39.2995 29.2717 39.3198V37.5854C28.9727 37.5339 28.7649 37.4854 28.7649 37.4854C23.0651 36.0347 18.8621 31.1836 18.8621 24.9649C18.8621 20.2001 21.6479 16.3471 25.7626 14.1871V11.8458C19.8491 13.7824 15.6084 18.7821 15.6084 24.9651C15.6084 28.0226 16.4055 30.4116 17.7949 32.5511C14.1379 31.9086 12.5619 29.3576 12.5619 24.9651V8.0003H12.558H6.0005L6 8ZM23.2828 8.00928V9.75488H29.2668V8.00928H23.2828ZM31.2103 11.0498C30.5496 11.0498 29.8986 11.0884 29.2586 11.165L29.2713 24.9648C29.2713 27.6488 28.8838 29.2328 27.5101 30.9218C25.9988 29.2543 25.7601 27.3603 25.7601 24.9648C25.7601 23.6885 25.7621 17.6165 25.7621 17.6165C23.7565 19.5565 22.5023 21.9665 22.5023 24.9648C22.5023 31.2373 27.3458 36.1358 33.2568 36.1358C35.2853 36.1358 37.6253 35.6398 39.3326 34.4785L38.9019 33.8355C36.5975 35.0117 31.9197 35.2849 29.0617 32.6099C31.4782 30.8264 32.6969 28.5439 32.6969 24.9649V12.6881C36.7442 12.6881 39.1712 15.0954 39.3019 17.8541L40.8073 18.15L41.862 12.0085L40.0695 11.6599L39.8508 12.9705C36.618 11.3445 33.9055 11.0501 31.2105 11.0501L31.2103 11.0498Z"
			fill="white"
		/>
	</svg>
</div>

<div class="container">
	<div class="menu">
		{#each buttons as b}
			{#if b.popup == true}
				<!--<button class='menu_button'><img src="{b.icon}" alt="icon"> {b.label} <img src="{popupIcon}" alt="popup" style="margin-left: auto"></button>-->
				<a href={b.id} target="_blank" class="menu_button">
					<img src={b.icon} alt="icon" />
					{b.label}
					<img
						src={popupIcon}
						alt="popup"
						style="display:flex; margin-left: auto"
					/>
				</a>
			{:else}
				<!--<button onclick={() => redirect(b.id)} class={$page.url.pathname === b.id ? 'current_button' : 'menu_button'}><img src="{b.icon}" alt="icon"> {b.label} <img src={$page.url.pathname === b.id ? rectangle : ''} alt="" style="margin-left: auto"></button>-->
				<a
					href={b.id}
					class={$page.url.pathname === b.id
						? "current_button"
						: "menu_button"}
				>
					<img src={b.icon} alt="icon" />
					{b.label}
					<img
						src={$page.url.pathname === b.id ? rectangle : ""}
						alt=""
						style="display:flex; margin-left: auto"
					/>
				</a>
			{/if}
		{/each}
	</div>

	<div class="main_screen">
		{@render children()}
	</div>
</div>

<style>
	.red_box {
		background: var(--Primary-UC-Red, #e00122);
		display: flex;
		padding: 10px 20px;
		align-items: center;
		gap: 20px;
		align-self: stretch;
		position: fixed;
		top: 0;
		width: calc(100% - 40px);
	}

	.container {
		display: flex;
		width: 100%;
		height: 100vh;
	}

	.menu {
		background: var(--Secondary-Grey, #f3f3f3);
		display: 1;
		width: 300px;
		flex-direction: column;
		height: 100vh;
		position: fixed;
		top:70px;
	}

	.main_screen {
		display: 1;
		flex-direction: column;
		padding: 10px;
		margin-top:70px;
		margin-left: 300px;
	}

	.menu_button {
		display: flex;
		height: 68px;
		padding: 10px 20px;
		align-items: center;
		gap: 20px;
		border: 0px;
		text-decoration: none;
		color: var(--Primary-UC-Black);

		box-sizing: border-box;
	}
	.current_button {
		background: rgba(255, 255, 255, 0.7);
		display: flex;
		height: 68px;
		padding: 10px 0 10px 20px;
		align-items: center;
		gap: 20px;
		text-decoration: none;
		color: var(--Primary-UC-Black);

		box-sizing: border-box;
	}
	.uc_logo {
		margin-left: auto;
	}
</style>
