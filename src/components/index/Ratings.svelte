<script>
  export let stars, name, text;
</script>

<style>
  .ratingWrapper {
    display: flex;
    flex-direction: column;
    border: 3px var(--brandingColor) solid;
    border-radius: var(--mainBorderRadius);
    padding: 40px;
    width: 500px;
    margin: 40px auto;
  }
  .text {
    margin-top: 10px;
  }
  @media screen and (max-width: 1200px) {
		.ratingWrapper {
			width: 300px;
      margin: 10px auto
		}
	}
</style>

<div class="ratingWrapper">
  <div>
    {#each {length: stars} as i}
      <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="55.617" height="54.004" viewBox="0 0 55.617 54.004">
        <defs>
          <filter id="Icon_awesome-star" x="0" y="0" width="55.617" height="54.004" filterUnits="userSpaceOnUse">
            <feOffset dy="3" input="SourceAlpha"/>
            <feGaussianBlur stdDeviation="3" result="blur"/>
            <feFlood flood-opacity="0.161"/>
            <feComposite operator="in" in2="blur"/>
            <feComposite in="SourceGraphic"/>
          </filter>
        </defs>
        <g transform="matrix(1, 0, 0, 1, 0, 0)" filter="url(#Icon_awesome-star)">
          <path id="Icon_awesome-star-2" data-name="Icon awesome-star" d="M18.232,1.252l-4.591,9.309-10.273,1.5A2.251,2.251,0,0,0,2.123,15.9L9.555,23.14,7.8,33.37a2.249,2.249,0,0,0,3.262,2.37l9.19-4.83,9.19,4.83A2.25,2.25,0,0,0,32.7,33.37L30.945,23.14,38.377,15.9a2.251,2.251,0,0,0-1.245-3.839l-10.273-1.5L22.268,1.252a2.252,2.252,0,0,0-4.036,0Z" transform="translate(7.56 6)" fill="#e1ca00"/>
        </g>
      </svg>
    {/each}
  </div>
  <h3>{name}</h3>
  <div class="text">{text}</div>
</div>