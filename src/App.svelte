<script>
  import Header from "./Header.svelte";
  import Buttons from "./Buttons.svelte";
  import PlayerLabel from "./PlayerLabel.svelte";
  import GameArea from "./GameArea.svelte";
  export let name;
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<div class="container">
  <Header />

  <Buttons />

  <PlayerLabel />

  <GameArea />
</div>

<!-- <h1>Hello {name}!</h1> -->
