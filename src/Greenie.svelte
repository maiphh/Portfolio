<script>
import { fly } from 'svelte/transition';
let s1 = true;
let s2 = false;
let s3 = false;
let s4 = false;
let s5 = false;
let s6 = false;
let s7 = false;

function choose1() {
    s1 = true;
    s2 = false;
    s3 = false;
    s4 = false;
    s5 = false;
    s6 = false;
    s7 = false;
}

function choose2() {
s1 = false;
s2 = true;
s3 = false;
s4 = false;
s5 = false;
s6 = false;
s7 = false;

}

function choose3() {
s1 = false;
s2 = false;
s3 = true;
s4 = false;
s5 = false;
s6 = false;
s7 = false;

}

function choose4() {
s1 = false;
s2 = false;
s3 = false;
s4 = true;
s5 = false;
s6 = false;
s7 = false;

}

function choose5() {
s1 = false;
s2 = false;
s3 = false;
s4 = false;
s5 = true;
s6 = false;
s7 = false;

}

function choose6() {
s1 = false;
s2 = false;
s3 = false;
s4 = false;
s5 = false;
s6 = true;
s7 = false;

}

function choose7() {
s1 = false;
s2 = false;
s3 = false;
s4 = false;
s5 = false;
s6 = false;
s7 = true;

}

</script>



<style>

@font-face {
    font-family: "mafins";
    src: url(..\src\fonts\Mafins.ttf) format("truetype");
}

html {
    font-family: "mafins";
}

.title {
  display: flex;
  align-items: center;
}

.title h1 {
width: 100vw;
font-size: 60px;
color: #285430;
font-weight: normal;
  text-align: center;
}

.container {
  display: grid;
  grid-template-columns: auto auto;
  grid-column-gap: 10vw;

}

.left {
display: grid;
justify-content: end;
margin-top: 30px;
}


@media only screen and (max-width: 768px) {
.container {
grid-template-columns: auto
}

.left {
place-items: center;
justify-content: center;
}

.right {
display: grid;
place-items: center;
}
}


.placeholder {
  width: 330px;
  height: 630px;
  position: relative;
  align-items: center;
  justify-content: center;
  display: flex;

}

.holder {
  position: absolute;
  height: 100%;
  width: 100%;
}

.phone {
 position: absolute;
 height: 70%;
 width: 70%;

}

.right {
margin-top: 20px;

}

.overview {
width: 470px;
margin-bottom: 40px;
color: #5F8D4E;
}
.section {
  display: grid;
  grid-template-columns: 70px 400px;
  margin-bottom: 30px;
  cursor: pointer;
}

@media only screen and (max-width: 768px) {
.section {
grid-template-columns: 30px 300px;
}

.right {
margin-top: 50px;
}
}

.dot {
   background: #385a94;
   border-radius: 50%;
   height: 10px;
   width: 10px;
   background-color: #A4BE7B;
}

.active-section .dot {
 background-color: #5F8D4E;
}

.active-section .content {
color: #5F8D4E !important;
}

.active-section .number {
color: #285430 !important;
}

.number {
color: #958D8D;
}

.content {
grid-column: 2/3;
color: #393939;
}
</style>



<main>

<div class="title">
  <h1> WHAT IS GREENIE?</h1>
</div>

<div class="container">

  <div class="left">
      <div class="placeholder">
      <img src="src\assets\greenie\placeholder.png" alt="" class="holder">

      {#if s1}
      <img src="src\assets\greenie\0.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s2}
      <img src="src\assets\greenie\1.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s3}
      <img src="src\assets\greenie\2.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s4}
      <img src="src\assets\greenie\5.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s5}
      <img src="src\assets\greenie\4.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s6}
      <img src="src\assets\greenie\8.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {:else if s7}
      <img src="src\assets\greenie\9.png" alt="" class="phone" in:fly="{{x:50,duration: 1500,delay:500}}" out:fly="{{x:-50,duration: 800}}">
      {/if}
      </div>


  </div>

  <div class="right">
      <div class = overview>
      Greenie is a mobile application aims to reduce the world's plastic waste by giving rewards for users who really care about the environment.
      </div>
      <div class="section {s1?"active-section":""}" on:click={choose1}>
        <div class="dot">

        </div>

        <div class="number">
        01
        </div>

        <div class="content">
          Login with phone or Gmail. If user choose phone, there will be an OTP send directly to the entered phone number.
        </div>
      </div>

      <div class="section {s2?"active-section":""}"  on:click={choose2}>
        <div class="dot">

        </div>

        <div class="number">
        02
        </div>

        <div class="content">
          Main Page display username, user's GPs, number of plants in the game and featuring brands.
        </div>
      </div>

      <div class="section {s3?"active-section":""}"  on:click={choose3}>
        <div class="dot">

        </div>

        <div class="number">
        03
        </div>

        <div class="content">
          QR code which user can give to the cashier to recieve rewards like GPs or Vouchers.
        </div>
      </div>

      <div class="section {s4?"active-section":""}"  on:click={choose4}>
        <div class="dot">

        </div>

        <div class="number">
        04
        </div>

        <div class="content">
          Mystery boxes contain plants with different rarities to plant in the Mini Planet.
        </div>
      </div>

      <div class="section {s5?"active-section":""}"  on:click={choose5}>
        <div class="dot">

        </div>

        <div class="number">
        05
        </div>

        <div class="content">
          Mini Planet is the place to earn GPs. The more trees planted, the more GPs it gives.
        </div>
      </div>

      <div class="section {s6?"active-section":""}"  on:click={choose6}>
        <div class="dot">

        </div>

        <div class="number">
        06
        </div>

        <div class="content">
          GP Shop contains Vouchers and Items which can be bought with GPs.
        </div>
      </div>

      <div class="section {s7?"active-section":""}"  on:click={choose7}>
        <div class="dot">

        </div>

        <div class="number">
        07
        </div>

        <div class="content">
          Personal Profile which can be customizable.
        </div>
      </div>

  </div>

</div>


</main>
