<script>
  let openMenu = false;
  let firstTouch;

  const touchStart = e => {
    firstTouch = e.touches[0].clientY;
  }

  const touchMove = e => { 
    if(firstTouch <  e.touches[0].clientY - 100) {
      openMenu = false;
    }
  }

  const links = [
    ['#Fueherscheinklassen', 'Führerscheinklassen'],
    ['#Preise', 'Preise'],
    ['#Fahrzeuge', 'Fahrzeuge'],
    ['#Kontakt', 'Kontakt'],
    ['#Information', 'Information'],
  ]
</script>

<style>
  header {
    background-color: var(--brandingColor);
    display: flex;
    flex-direction: row;
    align-items: center;
    color: var(--white);
    padding-left: 40px;
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100vw;
    z-index: 99999;
    box-shadow: var(--mainBoxShadow);
  }
  header h3 {
    padding-right: 10px;
  }
  nav {
    padding: 18px;
  }
  nav a {
    padding: var(--mainPadding);
    border-top: 3px var(--brandingColor) solid;
    border-bottom: 3px var(--brandingColor) solid;
  }
  nav a:hover {
    border-bottom: 3px var(--white) solid;
  }
  footer {
    margin-top: 50px;
    text-align: center;
  }
  footer a {
    padding: var(--mainPadding);
  }

  .openedMenu {
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 100vw;
    background-color: #ffffff;
    position: fixed;
    bottom: 0px;
    left: 0px;
    box-shadow: var(--mainBoxShadow);
    animation-name: slideUp;
    animation-duration: 0.50s;
  }
  .openedMenu a {
    display: block;
  }
  .closedMenu {
    animation-name: slideUp;
    animation-direction: reverse;
    animation-duration: 0.50s;
  }
  .menuBtn {
    display: none;
    border: none;
    background-color: transparent;
    fill: var(--white);
  }

  @media screen and (max-width: 750px) {
    header {
      padding: var(--mainPadding);
    }
    nav {
      display: none;
      align-items: center;
      justify-content: flex-start;
      padding: 0;
    }
    nav a {
      color: var(--brandingColor);
      border: none;
    }
    .menuBtn {
      display: initial;
    }
  }
</style>

<header>
  <button class="menuBtn" on:click={() => openMenu = !openMenu}>
    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
      <path d="M3,6H21V8H3V6M3,11H21V13H3V11M3,16H21V18H3V16Z" />
    </svg>
  </button>
  <h3>Fahrschule</h3>
  <nav on:touchstart={e => touchStart(e)} on:touchmove={e => touchMove(e)} class={openMenu ? "openedMenu" : "closedMenu"}>
    {#each links as [url, value]}
      <a href={url}>{value}</a>
    {/each}
  </nav>
</header>
<slot />
<footer>
  <a href="https://kevin-sheard.com/Impressum">Impressum</a>
  <a href="#Datenschutz">Datenschutz</a>
  <a href="#Kontakt">Kontakt</a>
</footer>
