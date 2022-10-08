
<!--
    File Name:
        IntroBlock.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 17:25 GMT+8
    
    Description:
        props Format:
            buttonProps: [{Btn1_ID:target_url1}, {Btn2_ID:target_url2}, ...]
-->


<template>
<div class="intro-block">
    <IntroBlockDescription
        :nowHoveredButton="nowHoveredButton"
        :buttonProps="buttonProps"
    >

    </IntroBlockDescription>



    <IntroBlockButtonGroup 
        :buttonProps="buttonProps" 
        @emitHoveredButtonID="getHoveredButtonID"
    >
    </IntroBlockButtonGroup>
    
</div>
</template>

<script>
    import IntroBlockButtonGroup from './IntroBlock/IntroBlockButtonGroup.vue';
    import IntroBlockDescription from './IntroBlock/IntroBlockDescription.vue';

    export default {
        name:"IntroBlock",

        data(){
            return{
                buttonProps:{
                    "ECON I 作業1":"/",
                    "YT":"https://www.youtube.com/",
                    "FB":"https://www.facebook.com/"
                },

                nowHoveredButton:"Welcome To DDHB ML"
        }},

        methods:{
            getHoveredButtonID(ButtonID) {
                this.nowHoveredButton = ButtonID;
                //console.log("@IntroBlock: get button ID-", this.nowHoveredButton);
            }
        },

        components:{
            IntroBlockButtonGroup,
            IntroBlockDescription
        }
    }
</script>






<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .intro-block{
        width: 80%;
        height: 350px;
        margin: 5% auto;

        display: flex;
        flex-direction: row; 

        justify-content: center;
        /*align-items: center;*/
    }
</style>