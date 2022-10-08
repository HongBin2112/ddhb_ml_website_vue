
<!--
    File Name:
        IntroBlockButtonGroup.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 20:50 GMT+8
    
    Description:
        Make sure './IntroBlockButton.vue' exist before use this component.
        This component require parent component pass all props:
        Format:
            buttonProps: [{Btn1_ID:target_url1}, {Btn2_ID:target_url2}, ...]
-->


<template>
<div class="button-group">
    <template v-for="(targetPath, buttonID) in buttonProps" :key="buttonID">
        <IntroBlockButton 
            :buttonName="buttonID"
            :buttonTargetPath="targetPath"
            @emitButtonID="getHoveredButtonID"
        >

        </IntroBlockButton>
    </template>
</div>
</template>



<script>

    import IntroBlockButton from './IntroBlockButton.vue';

    export default {
        name:"IntroBlockButtonGroup",

        data(){
            return{
                nowHoveredButton:"none"
        }},

        props :{
            buttonProps:{
                type:Object,
                require:true
            }
        },

        methods:{
            getHoveredButtonID(ButtonID) {
                this.nowHoveredButton = ButtonID;
                //console.log("@IntroBlockButtonGroup get button ID:", this.nowHoveredButton);
            },

            emitHoveredButtonID: function(){
                this.$emit("emitHoveredButtonID", this.nowHoveredButton);
                //console.log("emit from button group:", this.nowHoveredButton);
            }

        },

        watch:{
            nowHoveredButton:{
                handler(newValue){
                    this.$emit("emitHoveredButtonID", newValue);
                    //console.log("nowHoveredButton change", newValue, oldValue);
                }
            }
        },


        components:{
            IntroBlockButton
        }
    }
</script>

<style scoped>

    .button-group{
        min-width: 30%;

        display: flex;
        flex-direction: column; 
        /*justify-content: center;*/
    }
</style>