<template>
  <button type="button" @click="onClickAge">Update Age Event</button>    <!-- emits event -->
  <button type="button" @click="ageChangeFn(3)">Update Age CB</button>  <!-- callback -->
  <p>The user is {{ age }} years old</p>
  <p>{{ ageDoubled }}</p>
</template>

<script>
export default {
  name: "User",
  props: {
    age: {
      type: Number,
      // required: true,
      // default: 20
      validator(value) {
        // this.onClickAge()  会返回 undefined
        return value < 130;
      },
    },
    ageChangeFn: Function,
  },
  emits: ["age-change"], // 这将是一个将从组件发出的事件数组，将添加年龄变化事件
  computed: {
    ageDoubled() {
      return this.age * 2;
    },
  },
  methods: {
    onClickAge() {
      this.$emit("age-change", 3); //通过调用函数来发出一个事件
    },
  },
};
</script>

