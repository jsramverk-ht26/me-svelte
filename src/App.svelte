<script>
  import { Router, Link, Route } from 'svelte-routing'
  import Me from './Me.svelte'
  import Report from './Report.svelte'
</script>

<Router>
  <div class="app">
    <nav>
      <ul>
        <li><Link to="/">Me</Link></li>
        <li><Link to="/report/kmom01">kmom01</Link></li>
      </ul>
    </nav>
    <Route path="/"><Me /></Route>
    <Route path="/report/:kmom" let:params>
      <Report kmom={params.kmom} />
    </Route>
  </div>
</Router>

<style>
  @import url('https://rsms.me/inter/inter-ui.css');

  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :global(html) {
    font-size: 100%;
    font-family: 'Inter UI', sans-serif;
  }

  .app {
    width: 62em;
    margin: 0 auto;
    padding: 2em 6em 8em;
    background-color: #0074d9;
    border-top: 4px solid #0be6d7;
    color: white;
  }

  :global(h1) { font-size: 8em; font-weight: 100; }
  :global(h2) { font-size: 6em; font-weight: 100; }
  :global(p)  { font-size: 2em; font-weight: normal; }

  ul { list-style-type: none; }

  li {
    display: inline;
    margin-right: 1em;
  }

  li :global(a) {
    text-decoration: none;
    color: white;
    font-size: 1.4em;
  }

  li :global(a:hover) { text-decoration: underline; }
</style>
