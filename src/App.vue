<template>
	<div class="px-4 sm:px-8 py-4">

		<header>
			<h1 class="text-4xl font-bold text-center text-red-500">Liftu neatbilstību apraksts</h1>
		</header>

		<main>

			<section id="input">
				<h2 class="text-2xl font-bold text-red-500">Input</h2>
				<ul>
					<li v-for="(nb, index) in neatbilstibas" class="text-xl" :key="index">
						<label>
							<input type="checkbox" v-model="nb.checked">
							{{ nb.name }}
						</label>
					</li>
				</ul>
			</section>

			<section id="output">
				<h2 class="text-2xl font-bold text-red-500">Output</h2>
				<ul>
					<li v-for="(nb, index) in neatbilstibas.filter(n => n.checked).sort((a, b) => a.name.slice(0,2) - b.name.slice(0,2))" class="text-base" :key="index">
						{{ nb.name }}
					</li>
				</ul>
				<!-- <pre>{{ neatbilstibas }}</pre> -->
			</section>

		</main>
	</div>
</template>

<script>
export default {
	data() {
		return {
			greeting: "Hello worlds",
			active: true,
			neatbilstibas: [
				{ name: '1.4 - Mašīntelpas durvīm nav brīdinājuma uzraksta "Lifta mašīntelpa - bīstami".', checked: false },
				{ name: '3.1 - Nevar atvērt mašīntelpu no iekšpuses bez atslēgas ja tā ir aizvērta no ārpuses ar atslēgu.', checked: false },
				{ name: '1.4 - Lūkai mašīntelpā nav brīdinājuma zīmes par nokrišanas draudiem.', checked: false },
				{ name: '3.1 - Mašīntelpā lūka ir bojāta', checked: false },
				{ name: '3.6 - Nav vādskriemeļa aizarga pret trošu noslīdēšanas.', checked: false },
				{ name: '3.6 - Nav vādskriemeļa aizsarga pret svešķermeņu iekļūšanas starp trosēm un rievām.', checked: false },
				{ name: '3.6 - Nav vādskriemeļa aizsarga pret trošu noslīdēšanas un svešķermeņu iekļūšanas starp trosēm un rievām.', checked: false },
				{ name: '3.6 - Eļļas noplūde no lifta mašīnas reduktora.', checked: false }
			]
		};
	},
	methods: {
		toggle() {
			this.active = !this.active;
		},
	},
};
</script>
