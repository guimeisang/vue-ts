<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ name }}</h1>
    <h1>{{ age }}</h1>
    <h1>{{ address }}</h1>
    <h1>{{ job }}</h1>
    <Project />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Project from "@/components/Project.vue";
@Component({
  components: {
    Project
  }
})
export default class HelloWorld extends Vue {
  @Prop() readonly msg!: string;
  @Prop({ default: "John doe" }) readonly name: string;
  @Prop({ required: true }) readonly age: number;
  @Prop(String) readonly address: string;
  @Prop({ required: false, type: String, default: "Developer" })
  readonly job: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
</style>
