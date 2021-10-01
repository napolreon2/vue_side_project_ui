<template>
  <div>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <v-card>
          <v-card-title class="headline">
            {{title}}
          </v-card-title>
          <v-card-text>
            {{content}}
          </v-card-text>
          <v-card-actions>
            <v-spacer/>
            <v-btn color="primary" @click="onClickBtnReq">서버요청</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>    
    </v-row>
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
    data(){
      return {
        title: '요청 받기 전',
        content: '요청버튼을 눌러보세요'
      }
    },
    methods:{
      onClickBtnReq(){
        const me = this; // scope

        // nuxt.config의 baseURL 불러오기
        axios.get(me.$axios.defaults.baseURL + '/main').then(res=>{
          let data = res.data;

          me.title = data.title;
          me.content = data.content;

        }).catch(e =>{
          alert('에러발생');
        })
      }
    }

  }
</script>

<style lang="scss" scoped>

</style>