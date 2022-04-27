<script lang="ts">
	import { page } from '$app/stores';
</script>

<header>
	<nav>
    <ul class="menu">
      <li>
        <button class="parent">☰</button>
    		<ul>
    			<li class:active={$page.path === '/'} class="menu_item"><a sveltekit:prefetch href="/" id="home">Home</a></li>
    			<li class:active={$page.path === '/about'} class="menu_item"><a sveltekit:prefetch href="/about">About</a></li>
          <li class:active={$page.path === '/todos'} class="menu_item"><a sveltekit:prefetch href="/projects">Todos</a></li>
    		</ul>
      </li>
    </ul>
	</nav>
</header>

<style>

  header {
    position: fixed;
    z-index: 99;
  }
  
	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		list-style: none;
		background-size: contain;
    width: 100px;
	}

  .menu {
    display: block;
    position: relative;
    width: 100%;
  }

  .parent {
    margin-top: 4px;
    margin-left: 4px;
    background-color: #444;
    color: white;
  }

  .menu ul {
    height: 0;
    left: 0;
    opacity: 0;
    position: absolute;
  }

  .menu li:hover ul {
    height: 3em;
    opacity: 1;
    transform: translateY(0px);
    transition: all .5s ease;
  }

  ul:not(.menu) {
    background: #333;
    transition: background 1s;
  }

	.menu_item {
		position: relative;
		height: 100%;
	}

	.menu_item.active {
		background-color: #04AA6D;
	}

  .menu_item:not(.active) {
    background-color: #333;
  }

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 1em;
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
    color: white;
	}

	a:not(.parent):hover {
		background: #111;
    transition: background 1s;
	}
</style>
