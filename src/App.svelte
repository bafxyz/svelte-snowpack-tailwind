<script>
	import "@/TailwindStyles.svelte";
	import { Route } from "tinro";
	import Lazy from "@/components/Lazy.svelte";
	import MainNav from "@/components/MainNav.svelte";
	import RouterTransition from "@/components/RouterTransition.svelte";
	import Dashboard from "@/routes/dashboard/index.svelte";
</script>

<MainNav />

<RouterTransition>
	<Route>
		<Route path="/">
			<Dashboard />
		</Route>

		<Route path="/profile/*">
			<Route path="/">
				<Lazy
					component={() => import('@/routes/profile/index.svelte')} />
			</Route>
			<Route path="/edit">
				<Lazy
					component={() => import('@/routes/profile/Edit.svelte')} />
			</Route>
		</Route>

		<Route fallback>
			<Lazy component={() => import('@/routes/oops/index.svelte')} />
		</Route>
	</Route>
</RouterTransition>
