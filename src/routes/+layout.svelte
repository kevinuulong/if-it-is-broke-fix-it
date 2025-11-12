<script>
	import favicon from '$lib/assets/favicon.svg';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="red_box">
</div>

{@render children()}

<div class="container">
	<div class="menu">
		<button class="menu_button">Home</button>
		<button class="menu_button">Missing Classes</button>
		<button class="menu_button">Future Classes</button>
		<button class="menu_button">Completed Classes</button>
		<button class="menu_button">Planned Classes</button>
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
</style>