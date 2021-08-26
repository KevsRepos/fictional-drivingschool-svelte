<script>
import CtaBtn from "../CtaBtn.svelte";

</script>
<style>
  .wrapper {
    background-image: url('/./images/fahrlehrer.jpg');
    background-position: center;
    background-repeat: no-repeat;
  }
  .heading {
    display: flex;
    height: 80vh;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  h1 {
    margin: 15px;
  }
</style>

<div class="wrapper">
  <div class="heading">
    <h1>Ich, Paul Fahrmeister</h1>
    <h1>Willkommen in meiner Fahrschule</h1>
    <CtaBtn route="#UeberMich" value="Mehr über Mich" />
  </div>
</div>