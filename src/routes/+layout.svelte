<script lang="ts">
  import '../app.css';
    
  let { children } = $props();
</script>
  
<nav class="navbar rounded-box shadow-base-300/20 shadow-sm">
  <div class="w-full md:flex md:items-center md:gap-2">
    <div class="flex items-center justify-between">
      <div class="navbar-start items-center justify-between max-md:w-full">
        <a href="/home" aria-label="Homepage Link">
          <svg data-component-name="svg" xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-primary mr-2" viewBox="0 0 20 20" fill="currentColor">
            <path data-component-name="path" fill-rule="evenodd" d="M9.504 1.132a1 1 0 01.992 0l1.75 1a1 1 0 11-.992 1.736L10 3.152l-1.254.716a1 1 0 11-.992-1.736l1.75-1zM5.618 4.504a1 1 0 01-.372 1.364L5.016 6l.23.132a1 1 0 11-.992 1.736L4 7.723V8a1 1 0 01-2 0V6a.996.996 0 01.52-.878l1.734-.99a1 1 0 011.364.372zm8.764 0a1 1 0 011.364-.372l1.733.99A1.002 1.002 0 0118 6v2a1 1 0 11-2 0v-.277l-.254.145a1 1 0 11-.992-1.736l.23-.132-.23-.132a1 1 0 01-.372-1.364zm-7 4a1 1 0 011.364-.372L10 8.848l1.254-.716a1 1 0 11.992 1.736L11 10.58V12a1 1 0 11-2 0v-1.42l-1.246-.712a1 1 0 01-.372-1.364zM3 11a1 1 0 011 1v1.42l1.246.712a1 1 0 11-.992 1.736l-1.75-1A1 1 0 012 14v-2a1 1 0 011-1zm14 0a1 1 0 011 1v2a1 1 0 01-.504.868l-1.75 1a1 1 0 11-.992-1.736L16 13.42V12a1 1 0 011-1zm-9.618 5.504a1 1 0 011.364-.372l.254.145V16a1 1 0 112 0v.277l.254-.145a1 1 0 11.992 1.736l-1.735.992a.995.995 0 01-1.022 0l-1.735-.992a1 1 0 01-.372-1.364z" clip-rule="evenodd"></path>
          </svg>
        </a>
        <a class="link text-base-content link-neutral text-xl font-bold no-underline whitespace-nowrap" href="/home">3D Print Pro</a>
        <div class="md:hidden">
          <button type="button" class="collapse-toggle btn btn-outline btn-secondary btn-sm btn-square" data-collapse="#logo-navbar-collapse" aria-controls="logo-navbar-collapse" aria-label="Toggle navigation">
            <span class="icon-[tabler--menu-2] collapse-open:hidden size-4"></span>
            <span class="icon-[tabler--x] collapse-open:block hidden size-4"></span>
          </button>
        </div>
      </div>
    </div>
    <div id="logo-navbar-collapse" class="md:navbar-end collapse hidden grow basis-full overflow-hidden transition-[height] duration-300 max-md:w-full">
      <ul class="menu md:menu-horizontal gap-2 p-0 text-base max-md:mt-2">
        <li><a href="/home">Home</a></li>
        <li><a href="home">About</a></li>
        <li><a href="/home">Careers</a></li>
      </ul>
    </div>
  </div>
</nav>
  
{@render children()} 