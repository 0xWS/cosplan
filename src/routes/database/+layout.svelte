<script>
	import Navbar from "$lib/components/core/Navbar.svelte";

	let menus = [
		{ name: "cosplan.me database", url: "/database" },
		{ name: "characters", url: "char" },
		{ name: "series", url: "series" },
	]
</script>

<div class="database">
	<Navbar menus={menus}/>
	<div class="content">
  		<slot />
	</div>
</div>

<style>
	.database {
		width: 100%;
	}
</style>
