<script>
  import { Router, Route, Link } from 'svelte-routing';
  import Main from './Main.svelte';
  import Portfolio from './Portfolio.svelte';
  import { onMount } from 'svelte';

  export let url = "";  

  onMount(() => {
    window.addEventListener('popstate', handlePopstate);

    return () => {
      window.removeEventListener('popstate', handlePopstate);
    };
  });

  function handlePopstate(event) {
    // Perform actions when the back button is pressed
    // For example, refresh the page
    window.location.reload();
  }  

</script>


<Router {url}>
  <nav>
    <Link to="/">Main</Link>
    <Link to="/portfolio">Portfolio</Link>    
  </nav>
  <div>
    <Route path="/"><Main /></Route>
    <Route path="/portfolio" component={Portfolio} />
  </div>  
</Router>
