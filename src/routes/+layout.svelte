<script>
	import Header from '../components/Header.svelte';
	import Tokens from '../components/Tokens.svelte';

	import '../app.css';
</script>

<div class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm">
	<div class="fixed bottom-0 w-full duration-200 flex p-10 z-[10]">
		<button>
			<i class="fa-solid fa-arrow-up" />
		</button>
	</div>
	<Header />
	<slot />
	<Tokens />
</div>