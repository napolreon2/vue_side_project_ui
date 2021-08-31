<template>
  <div>
    <input v-model="text" class="input">
    <v-btn name="add_butotn" @click="add(); add_list();" class="add_button"
      elevation="4"
    >
      ADD
    </v-btn>
    <div v-for="i in list" :key="i">
      ({{i}}) 문도, 가고 싶은 데로 간다    &emsp;    아니다, &emsp;  문도, 가고 싶은대로 간다
    </div>
    
    
  </div>
</template>

<script>
  export default {
    data () {
      return {
        text: 1,
        list: [1]
      }
    },
    methods: {
      add: function () {
        this.text = this.text + 1
      },
      add_list: function () {
        this.list.push(this.text)
        console.log(this.list)
      }
    }
  }
</script>

<style>
.input {
  color: white;
}

v-btn.add_button {
  color: white;
  background-color: lightsteelblue;
  display: inline-block;
}
</style>