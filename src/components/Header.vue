
<!--
    File Name:
        Header.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 01:08 GMT+8
    
    Description:
        vue component. 
        use "import Header from 'PATH/Header.vue'" and add "Header" to App component.
-->


<template>
<div id="header" class="container">
    <header class="d-flex flex-wrap align-items-center justify-content-center justify-content-md-between py-3 mb-4 border-bottom">
        
            
        <a v-bind:href="brand.href" class="d-flex align-items-center col-md-3 mb-2 mb-md-0 text-dark text-decoration-none">
            <img class="bi me-2" v-bind:src="brand.imgSrc" width="36" height="36">
            <span id="brand-content-font" class="fs-4">{{brand.text}}</span> 
        </a>


        <ul id="menu-list" class="nav col-12 col-md-auto mb-2 justify-content-center mb-md-0">
            <li><button @click="buttonGoTo('/')">Home</button></li>
            <li><button @click="buttonGoTo('/')">Features</button></li>
            <li><button @click="buttonGoTo('/')">Pricing</button></li>
            <li><button @click="buttonGoTo('/')">FAQs</button></li>
            <li><button @click="buttonGoTo('https://www.facebook.com/')">About</button></li>
        </ul>

        <div class="col-md-3 text-end">
            <form class="col-12 col-lg-auto mb-3 mb-lg-0 me-lg-3" role="search">
                <input type="search" class="form-control" placeholder="Search..." aria-label="Search" autocomplete="off">
            </form> 
        </div>
    </header>
</div>

</template>

<script>
    import "bootstrap";
    import "bootstrap/dist/css/bootstrap.css";


    export default {
        name:"Header",

        data(){
            return {

                brand:{
                    href:"/",
                    imgSrc:require("../assets/logo.png"),
                    text:"DDHB ML"
                }

            }
        },

        props: {
            msg: String
        },

        methods: {
            buttonGoTo:function(href){
                window.location.href=href;
            }
        }
    }
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    #header{
        max-width:100%; 
        min-height: 15%;
        background-color:#F5F5F5;
        box-shadow:2px 10px 16px -4px rgba(0,0,0,0.2);
    }

    #brand-content-font{
        /*
        font-family:"cwTeXYen";
        font-weight: bold;
        */
        font-size:1.25em;
    }

    #menu-list a{
        font-family:"cwTeXYen";
        font-size:1.25em;
        font-weight: bold;
    }

    #menu-list button{
        height: 100%;
        margin-right: 10px;
        margin-left:10px;

        outline:none;
        background-color: transparent;
        border: none;
    
        font-family:"cwTeXYen";
        font-size:1.3em;
        font-weight: bold;
    
        transition : 0.25s ease-in;
    }
    
    #menu-list button::after{
        content:" ";
        display:block; 
        width: 0%;
        height: 2px;
        background-color: #000;
        transition: .3s;
      }
    
    #menu-list button:hover{
        opacity : 1;
        transform : scale(1.05);
    }
    
    #menu-list button:hover::after{
        width:100%;
    }


  
</style>