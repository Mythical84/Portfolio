<script lang="ts">
  export let color

  function onClick() {
    alert("test")
  }
</script>

<main>
  <div id="container" on:click={onClick} style="--color: {color}">

  </div>
</main>

<style>
  #container {
    height: 100px;
    background: black;
    width: 200px;
    float:left;
    border: 2px solid var(--color);
    margin-left: 15px;
    margin-top: 15px;
    transform: translateY(0px) translateX(0px);
    box-shadow: 0px 0px #888888;
    transition: all .1s;
    border-radius: 7px;
  }

  #container:hover {
    transform: translateY(-3px) translateX(-3px);
    box-shadow: 5px 10px #888888;
    transition: all .1s;
  }
</style>