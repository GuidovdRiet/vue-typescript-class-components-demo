<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ firstName }}</h1>
    <h1>{{ lastName }}</h1>
    <h1>{{ fullName }}</h1>
    <h4>{{ counter }}</h4>
    <button @click="incrementCounter()">Press Me</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: number;

  private firstName: string = "First";
  private lastName: string = "Last";
  private counter: number = 0;
  private zip: string = "zip";

  private mounted() {
    return null;
  }

  get fullName(): string {
    return `${this.firstName} ${this.lastName}`;
  }

  private incrementCounter() {
    this.counter++;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
