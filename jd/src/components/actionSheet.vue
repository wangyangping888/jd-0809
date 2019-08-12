<template>
  <div>
    <div class="weui-mask" id="iosMask" :style="{opacity:show?1:0,display:show?'block':'none'}" @click="quxiao" ></div>
    <div class="weui-actionsheet " id="iosActionsheet" :class="show?'weui-actionsheet_toggle':''">
      <div class="weui-actionsheet__title">
        <p class="weui-actionsheet__title-text">{{title}}</p>
      </div>
      <div class="weui-actionsheet__menu">
        <div class="weui-actionsheet__cell" v-for="(item,index) in arr" :key="index" @click="dian(index,$event)">{{item}}</div>
      </div>
      <div class="weui-actionsheet__action">
        <div class="weui-actionsheet__cell" id="iosActionsheetCancel" @click="quxiao">取消</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
        show:{
            type:String,
            default:""
        },
        title:"标题"

    };
  },
  props: {
    value: {
      type: Boolean,
      default: false
    },
    arr:{
        type:Array,
        default:function(){
            return []
        }
    }
    
  },
  computed: {
    
  },
  methods: {
    quxiao:function(){
        this.show=!this.show
        this.$emit("input",this.show)
    },
    dian:function(a,b){
        console.log(this.arr[a])
        console.log(b)

        
    }

  },
  watch: {
    value:function(val){
        this.show = val
    }
  },
  created: function() {
    this.show = this.value
  }
};
</script>
<style lang="less">
</style>