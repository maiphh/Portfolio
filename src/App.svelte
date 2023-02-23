
<script>
 import { fade, blur, fly, slide, scale, } from "svelte/transition";
let ava1 = true;
let ava2 = false;

function hoverAva() {
ava1 = !ava1;
ava2 = !ava2;

}

</script>

<main>
{#if ava1}
  <img src="src\assets\ava.png" alt="ava" class="ava" id="ava"  on:mouseover={hoverAva} transition:slide={{duration:500}}>
{:else if ava2}
  <img src="src\assets\ava2.png" alt="ava" class="ava" id="ava2" on:mouseleave={hoverAva} transition:slide={{duration:500}}>
{/if}

{#if ava1}
  <div class="eyes" >
    <img src="src\assets\eye.png" class="eye" style="top: 101px; left: 36px" transition:slide={{duration:500}}>
    <img src="src\assets\eye.png" class="eye" style= "top:101px; right:31px" transition:slide={{duration:500}}>
  </div>
{/if}




</main>


<style>

main {
  display: grid;
  grid-template-columns: auto auto auto;
  place-items: center;
  min-height: 100vh;
  position: relative;
}

.ava {
  position: absolute;
  height: 60vh;
  bottom: 0px;
}

.eyes, .eye {
  position: absolute;
}

.eye {
  height: 5vh;
}

#ava2 {
cursor: pointer;
}

.item1{

}
</style>
