<template>
	<div v-bind:class="{gym:true, selectedGym:!selectedGym}" >
		<img :src="g.image" :alt="'Gym #'+index">
		Gym #{{index+1}}<br>
		Street: {{g.street}}<br>
		Price: {{g.price}}/3Hour<br>
		<b-button v-bind:type="{'is-link':true, 'is-light':selectedGym}" @click="selectGym(index)">
			{{selectedGym?'Choose':'Gym selected'}}
		</b-button>
	</div>
</template>

<script>
export default {
	props: {
		g: Object,
		index: Number,
		selectedGym: Boolean
	},
	methods: {
		selectGym(index){
			this.$parent.selectedGym = index
		}
	}
}
</script>

<style scoped>
	.gym{
		width: 300px;
		overflow: hidden;
		margin: 10px;
		text-align: center;
		border-radius: 22px;
		padding-bottom: 10px;
	}
	.selectedGym{
		border: 1px solid #8c67ef;
	}
	.gym img{
		width: 100%;
		height: 180px;
		border-radius: 20px;
	}
</style>