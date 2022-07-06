<script setup>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import nbs from "./data";
const checked = ref(true);
console.log(nbs.length);
</script>

<template>
	<div class="px-16 py-4">
		<header>
			<HelloWorld msg="Liftu neatbilstību apraksts" />
			<HelloWorld :msg="greeting" />
		</header>
		<p>
			<input type="text" v-model="greeting" />
		</p>
		<button v-bind:class="
			active ? 'bg-slate-400 px-4 py-2 text-white hover:bg-slate-600' : 'bg-red-400 px-4 py-2 text-white hover:bg-red-600'
		" v-on:click="toggle">
			Click me
		</button>
		<main>
			<p v-for="(nb, index) in nbs" class="text-base" :key="index">
				<input type="checkbox" id="checkbox" v-model="checked" />
				<label for="checkbox">{{ checked }} - index {{ index }} </label><br />
				{{ nb }}
			</p>
		</main>
	</div>
</template>

<script>
export default {
	data() {
		return {
			greeting: "Hello worlds",
			active: true,
		};
	},
	methods: {
		toggle() {
			this.active = !this.active;
		},
	},
};
</script>
