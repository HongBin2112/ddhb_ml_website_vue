
<!--
    File Name:
        MoreArticles.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 23:45 GMT+8
    
    Description:
        You don't need to write key in data() articles, just write value.

        data() Format:
            articles: [
                {
                    title:String,
                    imgSrc:String,
                    articleUrl:String
                }, 
                {
                    title:String,
                    imgSrc:String,
                    articleUrl:String
                }, ...]
-->
<template>
<div id="more-articles">
    <h1>{{title}}</h1>

    <div class="articles">

        <transition-group
        appear
        name="animate__animated animate__bounce"
        enter-active-class="animate__fadeIn">

            <div v-for="(article, index) in articles" 
            :key="index"
            class="article-intro">

                <h3>{{article.title}}</h3>
                <a :href="article.articleUrl">
                    <img :src="article.imgSrc">
                </a>

            </div>

        </transition-group>

    </div>
</div>
</template>



<script>
    import 'animate.css';
    
    export default {
        name:"MoreArticles",

        data(){
            return {
                title:"More Articels",

                articles:[
                    {
                        title:"淺談 Convolution",
                        imgSrc:"https://dongdong-zoez.github.io/assets/bilateral.jpg",
                        articleUrl:"https://dongdong-zoez.github.io/"
                    },
                    {
                        title:"淺談 Convolution2",
                        imgSrc:"https://dongdong-zoez.github.io/assets/bilateral.jpg",
                        articleUrl:"https://dongdong-zoez.github.io/"
                    },
                    {
                        title:"淺談 Convolution3",
                        imgSrc:"https://dongdong-zoez.github.io/assets/bilateral.jpg",
                        articleUrl:"https://dongdong-zoez.github.io/"
                    },
                ]
        }},

    }
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#more-articles{
    width: 80%;
    margin: 5% auto;
}

.articles{
    display: flex;
    flex-direction: row; 
    justify-content: center;
    flex-wrap: wrap;
}
.article-intro{
    margin: 2% 2.5% 2% 2.5%;
}
.article-intro img{
    max-height: 300px;
    
    transition: 0.6s;
}

.article-intro img:hover{
    transform : scale(1.08);
}

h1{
    margin:16px auto;
    padding:0;
    font-weight: bold;
}

</style>