<script lang="ts">
  import Card from "$lib/Card.svelte"
  import { onMount } from 'svelte'

  let posts = []
  let cards = [
    { title: "Test", description: "Yeah i got nothing for you" },
    { title: "Test2", description: "Testing description" }
  ]

  onMount(async () => {
    var letters = "0123456789ABCDEF"
    let color = "#"
  
    for (let i = 0; i < cards.length; i++) {
      color = "#"
      for (let i2 = 0; i2 < 6; i2 ++) {
        color += letters[Math.floor(Math.random() * 16)]
      }
      cards[i]["color"] = color
    }
    /*
    const response = await fetch("https://api.github.com/users/Mythical84/repos")
    posts = await response.json()
    alert(posts[0]["name"])
    */
  })
  
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<main>
  {#each cards as card}
    <Card color={card.color}/>
  {/each}
</main>

<style>

  main {
    margin-top: 50px;
    margin-left: 1vw;
    width: 95vw;
    height: 80vh;
    border: 1px solid black;
    border-radius: 25px;
  }
  
</style>
