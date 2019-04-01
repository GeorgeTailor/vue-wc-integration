<template>
	<form class="form">
		<zoo-select inputerrormsg="Name is required" labeltext="Name" :valid="nameValid">
			<select formControlName="select" slot="selectelement">
				<option v-for="option in options" :value="option.id">{{ option.firstName }} {{ option.lastName }}</option>
			</select>
		</zoo-select>
		<zoo-input labeltext="Input date field" inputerrormsg="Invalid value" infotext="Information text" :valid="dateValid">
			<input type="date" placeholder="Placeholder" slot="inputelement"/>
		</zoo-input>
		<zoo-button class="submit-button" size="small" v-on:click="submit()">
			<span slot="buttoncontent">Submit</span>
		</zoo-button>
	</form>
</template>

<script lang="ts">
	import { Component, Prop, Vue } from 'vue-property-decorator';

	@Component
	export default class HelloWorld extends Vue {
		private options = [
			{
				firstName: 'firstName',
				lastName: 'lastName'
			}
		];
		private name: any;
		private nameValid = true;
		private date: any;
		private dateValid = true;

		submit() {
			if (this.name && this.date) {
				return true;
			}

			if (!this.name) {
				this.nameValid = false;
			}
			if (!this.date) {
				this.dateValid = false;
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
	.form {
		max-width: 768px;
		margin: 0 auto;
	}
</style>
