# Integrating Vue project with zoo-web-components

## Setup

1. Run `npm i @zooplus/zoo-web-components --save` to install the package.
2. Modify you main `App.vue` and add the following line: `import "@zooplus/zoo-web-components";`
3. Use web components in your application:
```HTML

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
```

5. Add CSS Custom properties to your main styles:
```CSS
:root {
	--primary-mid: #3C9700;
	--primary-light: #66B100;
	--primary-dark: #286400;
	--primary-ultralight: #EBF4E5;
	--secondary-mid: #FF6200;
	--secondary-light: #F80;
	--secondary-dark: #CC4E00;
	--info-ultralight: #ECF5FA;
	--info-mid: #459FD0;
	--warning-ultralight: #FDE8E9;
	--warning-mid: #ED1C24;
}
```

