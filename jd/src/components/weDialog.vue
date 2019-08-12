<template>
<div id="dialog1" v-show="show">
    <div class="weui-mask" @click="zhezhao"></div>
    <div class="weui-dialog">
        <div class="weui-dialog__hd"><strong class="weui-dialog__title">弹窗标题</strong></div>
        <div class="weui-dialog__bd">弹窗内容，告知当前状态、信息和解决方法，描述文字尽量控制在三行内</div>
        <div class="weui-dialog__ft">
            <a href="javascript:;" class="weui-dialog__btn weui-dialog__btn_default" @click="zhezhao">取消</a>
            <a href="javascript:;" class="weui-dialog__btn weui-dialog__btn_primary">确定</a>
        </div>
    </div>
</div>
</template>
<style lang="less">

</style>
<script>
export default {
    data:function(){
        return{
            show:true
        }
    },
    props:{
        value:{
            type:Boolean,
            default:false
        }
    },
    methods:{
        zhezhao:function(){
            this.show =!this.show;
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