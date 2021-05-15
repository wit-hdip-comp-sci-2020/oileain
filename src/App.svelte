<script lang="ts">
  import Router from "svelte-spa-router";
  import Header from "./components/Header.svelte";
  import NotFound from "./pages/NotFound.svelte";
  import Home from "./pages/Home.svelte";
  import {setContext} from "svelte";
  import {Oileain} from "./services/oileain-api";

  setContext("oileain", new Oileain());

  let routes = {
    "/": Home,
    "*": NotFound,
  };
</script>

<svelte:head>
  <title>Oileain</title>
</svelte:head>

<Header title="Oileain"/>
<div class="uk-container">
  <Router {routes}/>
</div>
