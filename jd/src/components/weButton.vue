<template>
    <a href="javascript:;" class="weui-btn" :class=[typeStyle,disabledStyle,loadStyle] >
        <i class="weui-loading" v-show="loading"></i>
        <slot></slot>
    </a>
</template>
<style lang="less">
</style>
<script>
export default {
    props:{
        type:{
            type:String,
            default:""
        },
        disabled:{
            type:Boolean,
            default:false
        },
        loading:{
            type:Boolean,
            default:false
        }
    },
    computed:{
        typeStyle:function(){
            let s = ""
            switch(this.type){
                case 'primary' :
                s = "weui-btn_primary";break;
                case 'warning' :
                s = "weui-btn_warn";break;
                case 'default' :
                s = "weui-btn_default";break;
                default:
                s = "weui-btn_default";break;
            }
            return s;
        },
        disabledStyle:function(){
            return this.disabled?"weui-btn_disabled":""
            // let ret = ""
            // if(this.disabled==true){
            //     ret = "weui-btn_disabled"
            // }
            // return ret;
        },
        loadStyle:function(){
            return this.loading?"weui-btn_loading":""
        }
    }
}
</script>
