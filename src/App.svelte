<script>
	export let action;
	export let person;
	export let location;
	export let detail;
	export let participation;
	export let affection;
	export let group;
	export let badgroup;
	export let sensation;
	export let verybadgroup;
	export let badthing;
	export let goodthing;
	export let result;

	function calculate() {
		if(action && person && location && detail && participation && affection && group && badgroup && sensation && verybadgroup && badthing && goodthing){
			result = `Super ${action} @${person}, ça déboite, ya tout ce qu'on ne trouve que très rarement dans d'autres ${location}  (déjà rien que le fait qu'il y ai ${detail}) et ça particpe à ${participation} qui fait que les ${affection} se sentent faire partie de ${group} plutot que juste ${badgroup} avec une sensation de n'être que ${sensation} de ${verybadgroup}. Ca fait la difference entre ${badthing} et ${goodthing} dans ta vie comme en faisant partie.`;
		}
	}
</script>
<main>
	<h1>SUPER ACTION</h1>
	<p>Qu'est-ce qui est super ?</p><input type="text" bind:value={action} placeholder="action"/>
	<p>Qui a fait cette action ?</p><input type="text" bind:value={person} placeholder="Katia"/>
	<p>Où trouve-t-on rarement ce genre d'actions?</p><input type="text" bind:value={location} placeholder="boîtes"/>
	<p>Un détail sur l'action : </p><input type="text" bind:value={detail} placeholder="un point d'info"/>
	<p>A quoi cette action participe-t-elle ? </p><input type="text" bind:value={participation} placeholder="construction d'un squelette narratif permanent"/>
	<p>Qui est affecté par cette action? </p><input type="text" bind:value={affection} placeholder="employés"/>
	<p>Grâce à cette action, de quoi se sentent faire partie ces personnes ?</p><input type="text" bind:value={group} placeholder="aventure commune"/>
	<p>Comment ces personnes se sentiraient sans cette action ? </p><input type="text" bind:value={badgroup} placeholder="dans leur coin"/>
	<p>A quoi peuvent se comparer ces personnes (négatif) ? </p><input type="text" bind:value={sensation} placeholder="des pieces dispensables"/>
	<p>Un environnement négatif : </p><input type="text" bind:value={verybadgroup} placeholder="mécanique aux contours floux" />
	<p>Avec quoi cela fait la différence (quelque chose de négatif) : </p><input type="text" bind:value={badthing} placeholder="un job alimentaire" />
	<p>Et quelque chose de bien : </p><input type="text" bind:value={goodthing} placeholder="quelque chose que tu acceptes volontiers" />
	<button class="btn" on:click={calculate}> Générer </button>
	<p>Pavé : </p>
	{#if result}
	<p> { result } </p>
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
