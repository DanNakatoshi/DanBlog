<script>
	import { goto } from '$app/navigation';

	import Icon from '@iconify/svelte';
</script>

<div class="navbar bg-base-100">
	<div class="navbar-start">
		<!-- Drawer -->
		<div class="drawer">
			<!-- Drawer Button -->
			<input id="my-drawer" type="checkbox" class="drawer-toggle" />
			<div class="drawer-content">
				<!-- Page content here -->
				<label for="my-drawer" class="btn btn-primary drawer-button">
					<Icon icon="line-md:menu" />
				</label>
			</div>
			<!-- Drawer Contents -->

			<div class="drawer-side">
				<label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label>

				<ul class="menu p-4 w-80 min-h-full bg-base-200 text-base-content">
					<!-- Sidebar content here -->
					<li><a>Sidebar Item 1</a></li>
					<li><a>Sidebar Item 2</a></li>
				</ul>
			</div>
		</div>
		<!-- END Drawer -->
	</div>
	<div class="navbar-center" on:click={() => goto('/')}>
		<a class="btn btn-ghost text-xl">daisyUI</a>
	</div>
	<div class="navbar-end">
		<button class="btn btn-ghost btn-circle">
			<Icon icon="line-md:search" />
		</button>
		<button class="btn btn-ghost btn-circle">
			<div class="indicator">
				<Icon icon="line-md:bell" />
				<span class="badge badge-xs badge-primary indicator-item"></span>
			</div>
		</button>
	</div>
</div>
