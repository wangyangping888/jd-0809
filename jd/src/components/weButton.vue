<template>
    <a href="javascript:;" class="weui-btn" :class=[typeStyle,disabledStyle] ><slot></slot></a>
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
        }
    },
    computed:{
        typeStyle(){
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
        disabledStyle(){
            let ret = ""
            if(this.disabled==true){
                ret = "weui-btn_disabled"
            }
            return ret;
        }
    }
}
</script>
