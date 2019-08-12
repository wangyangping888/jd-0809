<template>
  <div class="home">
    <weButton type="primary">submit</weButton>
    <weButton type="warning">submit</weButton>
    <weButton type="default" loading>submit</weButton>
    <weButton type="primary" disabled>submit</weButton>
    <weButton type="primary" loading v-on:click="dianji">submit</weButton>
    <weButton type="primary" border="true" v-on:click="change">submit</weButton>
    <weButton type="warning" border="true">submit</weButton>
    <weButton type="default" loading border="true" >submit</weButton>
    <weDialog  v-model="show">{{title}}<template slot="sname">{{content}}</template></weDialog>
    <actionSheet v-model="act" :arr="list"></actionSheet>
  </div>
</template>

<script>
// @ is an alias to /src
import weButton from '@/components/weButton.vue'
import weDialog from '@/components/weDialog2.vue'
import actionSheet from '@/components/actionSheet.vue'

export default {
  name: 'home',
  data:function(){
    return {
      show:false,
      title:"登录",
      content:"弹窗内容",
      act:false,
      list:["拍照","从相册中选取","投票"]
    }
  },
  components: {
    weButton,
    weDialog,
    actionSheet
  },
  methods:{
    change:function(){
      this.show=!this.show
    },
    dianji:function(){
      this.act = !this.act
    }
  },
}
</script>
