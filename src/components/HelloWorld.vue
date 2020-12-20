<template>
  <form class="form" novalidate v-on:submit="submit($event)">
    <zoo-select>
      <select id="select-id1" formControlName="select" slot="select" required>
        <option disabled selected value="">Please select a value</option>
        <option
          v-for="option in options"
          v-bind:key="option.id"
          :value="option.id"
        >
          {{ option.firstName }} {{ option.lastName }}
        </option>
      </select>
      <label for="select-id1" slot="label">Name</label>
      <span slot="error">Name is required</span>
    </zoo-select>
    <zoo-input>
      <input id="input-id1" type="date" slot="input" required/>
      <label for="input-id1" slot="label">Input date field</label>
      <span slot="info">Information text</span>
      <span slot="error">Invalid value</span>
    </zoo-input>
    <zoo-button>
      <button type="submit">Submit</button>
    </zoo-button>
  </form>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  private options = [
    {
      firstName: "firstName",
      lastName: "lastName",
    },
  ];
  private name: any;
  private date: any;

  public submit(e: any) {
	  console.log(e)
    e.preventDefault();
    e.target.checkValidity();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="css">
.form {
  max-width: 768px;
  margin: 0 auto;
}
</style>
