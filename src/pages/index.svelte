<script>
	import CtaBtn from "../components/CtaBtn.svelte";
import Fahrlehrer from "../components/index/Fahrlehrer.svelte";
	import IconSections from "../components/index/IconSections.svelte";
	import Ratings from "../components/index/Ratings.svelte";

	const iconSectionInfo = [
		{
			icon: '/./images/icons/car.svg',
			heading: 'Mit dem Autoführerschein',
			subHeading: 'In 3 Monaten zum Autoführerschein',
			text: "Mit mindestens 12 theoretischen Stunden\nUnd mindesten 16 praktischen Fahrstunden",
			boldText: "Für NUR 95€ pro Fahrstunde",
			btnPath: "#CarInformation",
			direction: 'row'
		},
		{
			icon: '/./images/icons/motorcycle.svg',
			heading: 'Mit dem Motorradführerschein',
			subHeading: 'Motorrad fahren heißt Freiheit',
			text: "Mit 6 theoretischen Stunden und 12 praktischen Fahrstunden kannst auch Du die Freiheit erlangen",
			boldText: "Für NUR 70€ pro Fahrstunde",
			btnPath: "#MotorcycleInformation",
			direction: 'row-reverse'
		},
		{
			icon: '/./images/icons/truck.svg',
			heading: 'Mit dem LKW-Führerschein',
			subHeading: 'Beruflicher Fahrer werden?',
			text: "Mit 12 theoretischen Stunden und mindestens 15 praktischen Stunden erhälst Du bei uns deine LKW Führerschein",
			boldText: "Für NUR 155€ pro Fahrstunde",
			btnPath: "#TruckInformation",
			direction: 'row'
		},
	];

	const ratings = [
		{
			stars: 5,
			name: 'Sarah S',
			text: 'Tolle Fahrschule, und kompetente Lehrer. Die Fahrstunden haben Spaß gemacht und ich habe direkt bei der ersten Prüfung bestanden :)',
		},
		{
			stars: 5,
			name: 'Tom H',
			text: 'Super!! Habe die theoretische und praktische Prüfung direkt bestanden! Die Fahrlehrer sind nett und lustig. Volle 5 Sterne verdient!!',
		},
		{
			stars: 5,
			name: 'Ben W',
			text: 'Habe meinen Roller Führerschein da gemacht, dann Motorrad und letztendlich auch Auto. Kann ich nur empfehlen.',
		}
	];
</script>

<style>
  .landingBanner {
    height: 105vh;
    background-image: url('/./images/audi.jpg');
    background-size: cover;
  }
	.eyecatcher {
		position: absolute;
		top: 22vh;
		left: 40px;
	}
	.eyecatcher ul{
		background-color: var(--white);
		color: var(--black);
		list-style-image: url('/./images/icons/check.svg');
		font-size: 1.625rem;
		font-weight: bold;
		padding: 40px;
		padding-left: 0px;
		border-radius: var(--mainBorderRadius);
		display: block;
		padding-left: 80px;
		box-shadow: var(--mainBoxShadow);
		margin-bottom: 50px;
	}
	ul li {
		padding: 10px 0px;
	}
	.ratingSection {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
	}
	.lastCta {
		margin: 200px 0;
	}
	.lastCta span {
		display: flex;
		justify-content: center;
	}
	@media screen and (max-width: 750px) {
		.eyecatcher {
			width: 80vw;
			left: 50%;
			transform: translateX(-50%);
		}
	}
</style>

<div class="landingBanner">    
    <div class="eyecatcher">
			<ul>
				<li>Klasse B, BE, C, CE, A1, A2 und Rollerführerschein</li>
				<li>3 Theoriestunden pro Woche</li>
				<li>In nur 3 Monaten zum Autoführerschein</li>
			</ul>
			<CtaBtn value="Zur nächsten Stunden anmelden" route="#Anmelden" />
    </div>
</div>

<h1>Fahr wohin Du willst:</h1>
<section>
	<IconSections {...iconSectionInfo[0]} />
	<IconSections {...iconSectionInfo[1]} />
	<IconSections {...iconSectionInfo[2]} />
</section>

<h1>Gut bewertet</h1>
<section class="ratingSection">
	<Ratings {...ratings[0]} />
	<Ratings {...ratings[1]} />
	<Ratings {...ratings[2]} />
	<Ratings {...ratings[0]} />
	<Ratings {...ratings[1]} />
	<Ratings {...ratings[2]} />

</section>

<h1>Aber wer ist dein Lehrer?</h1>
<Fahrlehrer />

<div class="lastCta">
	<h1>Und jetzt zur Anmeldung</h1>
	<span ><CtaBtn route="#Anmelden" value="Los gehts" /></span>
</div>