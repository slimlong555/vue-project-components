<template>
  <h3>hi</h3>
  <greeting></greeting>
  <user :age="age" @age-change="updateAge" :ageChangeFn="updateAgeCB"></user>
</template>

<script >
import Greeting from "@/components/Greeting.vue";
import User from "@/components/User.vue";

export default{
   name: 'App',
   components: {
    Greeting,
    User,
  },
  data() {
    return {
      age: 20,
    };
  },
  methods: {
    updateAge(num) {
      this.age += num;
    },
    updateAgeCB(num) {
      this.age += num;
    },
  },
}// 这是应该添加数据方法、计算属性和观察者的地方。
</script>



