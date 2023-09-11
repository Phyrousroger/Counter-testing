<template>
  <div class="d-flex justify-content-between border m-3 border-primary rounded-1 align-items-center p-3">
    <h1>Counter: {{counter}}</h1>
    <div class="">
      <button @click="sub" class="btn btn-danger me-3">-</button>
      <button @click="add" class="btn btn-primary ">+</button>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      counter: this.start,
    }
  },
  props: ["start","index"],
  methods: {
    add() {
      // event emit
      this.$emit('aa',this.counter,this.index);
      return this.counter++;
    },
    sub(){
      return this.counter--;
    }
  },
}
</script>

<style scoped>

</style>