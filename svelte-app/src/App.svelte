<script>
  import { Router, Route } from 'svelte-routing';
  import Main from './Main.svelte';
  import Portfolio from './Portfolio.svelte';
</script>

<Router>
  <Route path="/" component={Main} />
  <Route path="/portfolio" component={Portfolio} />
</Router>
