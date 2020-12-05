<template>
  <form class="form">
    <zoo-select inputerrormsg="Name is required" :invalid="!nameValid">
      <select id="select-id1" formControlName="select" slot="selectelement">
        <option v-for="option in options" v-bind:key="option.id" :value="option.id">
          {{ option.firstName }} {{ option.lastName }}
        </option>
      </select>
      <label for="select-id1" slot="selectlabel">Name</label>
    </zoo-select>
    <zoo-input
      labeltext="Input date field"
      inputerrormsg="Invalid value"
      infotext="Information text"
      :invalid="!dateValid"
    >
      <input
        id="input-id1"
        type="date"
        placeholder="Placeholder"
        slot="inputelement"
      />
      <label for="input-id1" slot="inputlabel">Input date field</label>
    </zoo-input>
    <zoo-button v-on:click="submit()">
      <button type="button">Submit</button>
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
      lastName: 'lastName',
    },
  ];
  private name: any;
  private nameValid = true;
  private date: any;
  private dateValid = true;

  public submit() {
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
<style scoped lang="css">
.form {
  max-width: 768px;
  margin: 0 auto;
}
</style>
