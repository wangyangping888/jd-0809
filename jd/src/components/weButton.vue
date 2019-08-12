<template>
    <a href="javascript:;" class="weui-btn" :class=[typeStyle,disabledStyle,loadStyle] @click="$emit('click')">
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
        },
        border:{
            type:String,
            default:""
        }
    },
    computed:{
        typeStyle:function(){
            let ret = ""
            switch(this.type){
                case 'primary' :
                ret = this.border=="true"?"weui-btn_plain-primary":"weui-btn_primary";break;
                case 'warning' :
                ret = this.border=="true"?"weui-btn_warn":"weui-btn_warn";break;
                case 'default' :
                ret = this.border=="true"?"weui-btn_plain-default":"weui-btn_default";break;
            }
            return ret;
        },
        disabledStyle:function(){
            return this.disabled?"weui-btn_disabled":""
        },
        loadStyle:function(){
            return this.loading?"weui-btn_loading":""
        }
    }
}
</script>
