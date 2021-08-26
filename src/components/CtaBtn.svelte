<script>
  export let route, value;
</script>

<style>
  a {
    padding: var(--mainPadding) 55px;
    color: var(--white);
    background-color: var(--brandingColor);
    border-radius: var(--mainBorderRadius);
    font-family: var(--mainFont);
    transition: 0.10s ease-in;
    box-shadow: var(--mainBoxShadow);
  }
  a:hover {
    box-shadow: var(--hoverBoxShadow);
    transform: translateY(-3px);
  }
  @media screen and (max-width: 450px) {
    a {
      padding: var(--mainPadding);
    }
  }
</style>

<a href={route}>{value}</a>