
<!--
    File Name:
        Footer.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 17:25 GMT+8
    
    Description:
        vue component. 
        use "import Footer from 'PATH/Footer.vue'" and add "Footer" to App component.
-->


<template>
<div id="footer" class="container text-center">
    <div class="row align-items-center">

        <div class="col">
            <p class="sub-title">Contact Me</p>
            <p>{{contactInfo.myName}}</p>
            <p>✉️ E-mail : {{contactInfo.email}}</p>
        </div>

        <div class="col">
            <a id="back-to-top" href="#app">
                Back to top ▴
            </a>
        </div>

        <div class="col">
            <p class="sub-title">Web Design</p>
            <p> Hong Bin </p>
        </div>

    </div>
</div>
</template>



<script>
    import "bootstrap";
    import "bootstrap/dist/css/bootstrap.css";

    export default {
        name:"Footer",
    

        data(){
            return {

                contactInfo:{
                    myName:"Dong Dong",
                    email:"2lbry5230100@gmail.com",
                }

            }
        }

    }



</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    #footer{
        width: 100%;
        max-width:100%;
    
        background-color: #0b3e34a6;
        color: #FFFFFF;
    }


    #footer .col{
        height: 150px;

        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column; 
    }

    .sub-title{
        
        font-size:1.25em;
        font-weight: bold;

        color: #c3c3c3;
    }

    #back-to-top{
        font-size:1.25em;
        font-weight: bold;  
    }

    a{
        all: unset;
        cursor: pointer;
    }

    p{
        margin-bottom: 2px ;
        font-weight: bold;
    }

</style>