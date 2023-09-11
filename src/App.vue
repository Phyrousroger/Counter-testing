<!-- <template>-->
<!--  <h1 class="title">-->
<!--  Min ga lar par {{myName}}-->
<!--  </h1>-->

<!--  <h1 class="count">-->
<!--    counter:  <span>{{counter}}</span>-->
<!--  </h1>-->
<!--  <div class="">-->
<!--    <button v-on:click="sub()">Sub</button>-->
<!--    <button v-on:click="counter++">Add</button>-->
<!--  </div>-->
<!--  <hr>-->

<!--  <h1>My Fruits</h1>-->
<!--  <form action="" v-on:submit.prevent="addnewFruit()">-->
<!--    <input type="text" v-model="inputName">-->
<!--    <input type="number" v-model="inputPrice">-->
<!--    <button>Add</button>-->
<!--  </form>-->
<!--  <ul>-->
<!--    <li v-for="(fruit,index) in fruits" v-bind:key="index">{{fruit.name}}  >>{{fruit.price}}</li>-->
<!--  </ul>-->
<!--  <div>====================</div>-->
<!--  <p>total====>{{total}}</p>-->

<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      myName: "Phyo Thu Kha",-->
<!--      counter:0,-->
<!--      fruits:[-->
<!--          {-->
<!--            id:1,-->
<!--          name:"apple",-->
<!--          price:300-->
<!--          },-->
<!--        {-->
<!--          id:1,-->
<!--          name:"Orange",-->
<!--          price:200-->
<!--        },-->
<!--        {-->
<!--          id:1,-->
<!--          name:"Mango",-->
<!--          price:900-->
<!--        },-->
<!--        ],-->
<!--      input:null,-->
<!--    };-->
<!--  },-->
<!--  computed:{-->
<!--    fruitCount(){-->
<!--      return this.fruit.length;-->
<!--    },-->
<!--    total(){-->
<!--     return  this.fruits.reduce((p,c) => p+c.price,0)-->
<!--    }-->

<!--  },-->
<!--  methods: {-->
<!--    sub() {-->
<!--      if(this.counter>0){-->
<!--        this.counter&#45;&#45;-->
<!--      }-->
<!--    },-->
<!--    addnewFruit(){-->
<!--      const f={-->
<!--        id:this.fruitCount+1,-->
<!--        name:this.inputName,-->
<!--        price:this.inputPrice-->
<!--      };-->
<!--      console.log(f)-->

<!--      this.fruit.push(f);-->
<!--      this.inputName=null;-->
<!--      this.inputPrice=0;-->
<!--      this.input=null;-->

<!--    }-->
<!--  },-->

<!--}-->
<!--</script>-->

<!--<style>-->
<!--  .title{-->
<!--    color: aqua;-->
<!--    text-shadow: 0 0 20px  aqua;-->
<!--  }-->
<!--  .count span{-->
<!--    color: #48d223;-->
<!--    text-shadow: 0 0 10px #48d223;-->
<!--  }-->
<!--  input{-->
<!--    width: 300px;-->
<!--    padding: 10px;-->
<!--  }-->
<!--</style> -->
<template>
  <navbar/>
  <div class="m-3">
    <h1>Root Component</h1>
    <CounterCp
        @aa='showAdd'
        :start="num" :index="index" v-for="(num,index) in nums " :key="index"/>
    <Footer/>
  </div>



</template>

<script>
import CounterCp from "./components/CounterCp.vue";
import navbar from "./components/navbar.vue";
import Footer from "./components/Footer.vue";
export default {
  components: {
    CounterCp,
    navbar,
    Footer,
  },
  data() {
    return {
      title: "My Key Up",
      nums:[1,2,3],
    };
  },
  methods:{
    showAdd(x,y){
      console.log("show add",x,y);
      this.nums[y]=x
    }
  }
}


</script>

<style>

@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";




</style>
