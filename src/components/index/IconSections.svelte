<script>
  import CtaBtn from "../CtaBtn.svelte";
  export let icon, heading, subHeading, text, boldText, direction, btnPath;
</script>

<style>
  .rowWrapper {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding-bottom: 150px;
    border-bottom: 30px dashed var(--white);
    justify-content: space-around;
    width: 80vw;
    margin: auto;
    margin-bottom: 150px;
  }
  .columnWrapper {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 25vw;
  }
  .columnWrapper * {
    margin: 15px 0px;
  }
  img {
    height: clamp(250px, calc(15.625rem + ((1vw - 7.68px) * 15.191)), 425px);
  }

  @media screen and (max-width: 1200px) {
    .rowWrapper {
      align-items: flex-end;
    }
  }
  @media screen and (max-width: 850px) {
    .rowWrapper {
      flex-direction: column !important;
      align-items: center;
    }
    .columnWrapper {
      width: initial;
    }
    h2 {
      word-break: break-all;
    }
  }
</style>

<div class="rowWrapper" style={`flex-direction: ${direction}`}>
  <img src={icon} alt="icon" />
  <div class="columnWrapper">
    <h2>{heading}</h2>
    <h3>{subHeading}</h3>
    <p>{text}</p>
    <p><strong>{boldText}</strong></p>
    <CtaBtn route={btnPath} value="Näheres" />
  </div>
</div>
