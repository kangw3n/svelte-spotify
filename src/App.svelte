<script>
  import { Router, Route } from 'svelte-routing';
  import NavLink from './components/NavLink.svelte';

  import Home from './routes/Home.svelte';
  import About from './routes/About.svelte';
  import Track from './routes/Track.svelte';
  
  export let url = "";
</script>



<Router url="{url}">

<nav class="navbar navbar-inverse">
	<div class="container">
		<div class="navbar-header">
      <NavLink to="/" className="navbar-brand">vanilaES6Spotify</NavLink>
		</div>
		<div id="navbar" class="collapse navbar-collapse">
			<ul class="nav navbar-nav">
				<li>
          <NavLink to="/">Home</NavLink>
				</li>
				<li>
          <NavLink to="/about">About</NavLink>
				</li>
			</ul>
		</div>
	</div>
</nav>

<main class="content main">
  <Route path="/" component="{Home}" />
  <Route path="/about" component="{About}" />
  <Route path="/track/:id" component="{Track}" />

</main>


</Router>


<style>
.navbar-inverse .navbar-nav > li > a:hover, .navbar-inverse .navbar-nav > li > a.active {
	color: #2ebd59;
	font-weight: bolder;
}
</style>