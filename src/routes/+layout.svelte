<script lang="ts">
  import '../app.css';

  let { children } = $props();

  let expanded = $state(false);
</script>

<header class="py-4 bg-black sm:py-6">
	<div class="px-4 mx-auto max-w-7xl sm:px-6 lg:px-8">
		<div class="flex items-center justify-between">
			<div class="shrink-0">
        <a href="/home" aria-label="Homepage Link" class="flex items-center">
          <svg data-component-name="svg" xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-primary" viewBox="0 0 20 20" fill="currentColor">
              <path data-component-name="path" fill-rule="evenodd" d="M9.504 1.132a1 1 0 01.992 0l1.75 1a1 1 0 11-.992 1.736L10 3.152l-1.254.716a1 1 0 11-.992-1.736l1.75-1zM5.618 4.504a1 1 0 01-.372 1.364L5.016 6l.23.132a1 1 0 11-.992 1.736L4 7.723V8a1 1 0 01-2 0V6a.996.996 0 01.52-.878l1.734-.99a1 1 0 011.364.372zm8.764 0a1 1 0 011.364-.372l1.733.99A1.002 1.002 0 0118 6v2a1 1 0 11-2 0v-.277l-.254.145a1 1 0 11-.992-1.736l.23-.132-.23-.132a1 1 0 01-.372-1.364zm-7 4a1 1 0 011.364-.372L10 8.848l1.254-.716a1 1 0 11.992 1.736L11 10.58V12a1 1 0 11-2 0v-1.42l-1.246-.712a1 1 0 01-.372-1.364zM3 11a1 1 0 011 1v1.42l1.246.712a1 1 0 11-.992 1.736l-1.75-1A1 1 0 012 14v-2a1 1 0 011-1zm14 0a1 1 0 011 1v2a1 1 0 01-.504.868l-1.75 1a1 1 0 11-.992-1.736L16 13.42V12a1 1 0 011-1zm-9.618 5.504a1 1 0 011.364-.372l.254.145V16a1 1 0 112 0v.277l.254-.145a1 1 0 11.992 1.736l-1.735.992a.995.995 0 01-1.022 0l-1.735-.992a1 1 0 01-.372-1.364z" clip-rule="evenodd"></path>
          </svg>
          <span class="link text-base-content link-neutral text-xl font-bold no-underline whitespace-nowrap ml-2">3D Print Pro</span>
        </a>
			</div>

			<div class="flex md:hidden">
				<button type="button" class="text-white" onclick={() => expanded = !expanded} aria-expanded={expanded}>
					{#if !expanded}
						<svg class="w-7 h-7" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 6h16M4 12h16M4 18h16" />
						</svg>
					{:else}
						<svg class="w-7 h-7" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
						</svg>
					{/if}
				</button>
			</div>

			<nav class="hidden md:flex md:items-center md:justify-end md:space-x-12">
				<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Features</a>
				<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Pricing</a>
				<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Support</a>
                <a href="/home" class="btn btn-primary waves waves-light w-32"><span>Get started</span></a>
			</nav>
		</div>

		{#if expanded}
			<nav class="md:hidden">
				<div class="flex flex-col pt-8 pb-4 space-y-6">
					<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Features</a>
					<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Pricing</a>
					<a href="/home" class="text-base font-normal text-gray-400 transition-all duration-200 hover:text-white">Support</a>
				</div>
			</nav>
		{/if}
	</div>
</header>
  
{@render children()}