

<template>
<div>
    <transition
        appear
        name="animate__animated animate__bounce"
        enter-active-class="animate__fadeInRight"
    >
        <button @click="buttonGoTo()" @mouseover="emitButtonID()">{{buttonID}}</button>
    </transition>
    
</div>
</template>




<script>
    import 'animate.css';
    //Animate.css is a library of ready-to-use, cross-browser animations for use in your web projects
    //https://animate.style/ 
    //
    //About <transition> tag. please search "vue transition".
    //
    

    export default {
        name:"IntroBlockButton",

        data(){
            return {
                buttonID:this.buttonName
        }},

        props :{
            buttonName:{
                type: String,
                required: true
            },

            buttonTargetPath:{
                type:String,
                default:"/"
            }
        },

        methods:{
            buttonGoTo:function(){
                window.location.href=this.buttonTargetPath;
            },

            emitButtonID: function(){
                this.buttonID = this.buttonName;
                this.$emit("emitButtonID", this.buttonID);
                //console.log("from button self:", this.buttonID);
            }

        }

    }
</script>





<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    button{
        width:90%;

        margin: 16px auto;
        padding:2px 16px;

        outline:none;
        background-color: transparent;
        border: 2px #B0B0B0 solid;
        border-radius: 5px;
    
        /*font-family:"cwTeXYen";*/
        font-size:1.5em;
        font-weight: bold;
        color:#000000;
    
        opacity : 0.85;
        transition : 0.25s ease-in;
    }

    button:hover{
        opacity : 1;
        transform : scale(1.05);
    }
    
</style>