<template>
  <div id="dialog1" v-show="show">
    <div class="weui-mask"  @click="zhezhao"></div>
    <div class="weui-dialog">
        <div class="weui-dialog__hd" ><strong class="weui-dialog__title" ><slot></slot></strong></div>
        <div class="weui-dialog__bd"><slot name="sname"></slot></div>
        <div class="weui-dialog__ft">
            <a href="javascript:;" class="weui-dialog__btn weui-dialog__btn_default" @click="zhezhao" >取消</a>
            <a href="javascript:;" class="weui-dialog__btn weui-dialog__btn_primary">确定</a>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data:function(){
        return{
            show:true,
            title:"标题",
            
        }
       
    },
    props:{
        value:{
            type:Boolean,
            default:true
        }
    },
    methods:{
        zhezhao:function(){
            this.show = !this.show;
            this.$emit("input",this.show)
        }
    },
    watch:{
        value:function(val){
            this.show = val
        }
    },
    created:function(){
        this.show = this.value
    }
}
</script>

<style lang="less">

</style>