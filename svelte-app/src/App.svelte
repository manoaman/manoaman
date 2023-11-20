<script>
  import { Router, Route, Link } from 'svelte-routing';
  import Main from './Main.svelte';
  import Portfolio from './Portfolio.svelte';

  export let url = "";  
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
