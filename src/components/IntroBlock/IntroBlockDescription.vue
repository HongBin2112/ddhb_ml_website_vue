

<!--
    File Name:
        IntroBlockDescription.vue

    History:
        Version:1.0 , Author:Hong-Bin , Time: 2022/10/8 23:25 GMT+8
    
    Description:
        check again the button's ID in data() and props,
        if they don't match, it will not show text you want to show.

        data() Format:
            descriptions: {
                {Btn1_ID:description1}, 
                {Btn2_ID:description2}, ...
            }
-->

<template>
<div class="intro-block-description">
    <h1>{{nowHoveredButton}}</h1>
    <hr>

    <transition-group
      name="animate__animated animate__bounce"
      enter-active-class="animate__fadeInUp"
      leave-active-class="leave-immediately"
      >

        <div v-for="(targetPath, buttonID) in buttonProps" 
          :key="buttonID" 
          v-show="nowHoveredButton === buttonID">
            
                {{descriptions[buttonID]}}
            
        </div>
    </transition-group>
</div>
</template>




<script>
    import 'animate.css';
    
    export default {
        name:"IntroBlockDescription",

        data(){
            return {
                descriptions:{
                    "ECON I 作業1":`文章“What Dutch disease is, and why it's bad”前半部分解說Dutch-disease的由來，後半部分透過一些例子講述及討論其所造成的影響。\n
第一段以文章當年俄羅斯盧布貶值的例子引出Dutch disease。第二段說明來源:此現象名稱源自1977年《經濟學人》(The Economist)，用以描述那年荷蘭經濟困境。而該段後部分便在講述並解釋當時荷蘭所遭遇的經濟狀況。
第三段說明經濟學家提出其他Dutch disease的解釋:假設一個國家內貨幣數量固定，額外的外國貨幣流入最後會使其在國內的價值不斷降低，影響匯率，導致國家失去競爭力。
第四段則說明有些經濟學家認為Dutch disease並無不好，因為經濟本就該專注在怎麼最有效率的生產。後半段作者則舉例並說明，除非這些GDP中自然資源出口占比高的國家實現經濟多元化或降低實際匯率，否則Dutch disease將相當致命。
另一篇文章” Should the United States trade with other countries?”除最後一段外，主要在解釋並說明「比較利益(comparative advantage)」及其益處。末段則說明:現實情況遠比文章所舉例子更加複雜，國際貿易有好有壞。文末作者認為:國際貿易是能讓所有國家都獲得利益的，並非如戰爭般只有贏或輸。
`,

                    "YT":"this is YT description",
                    "FB":"this is FB description"
                }

        }},

        props :{
            nowHoveredButton:{
                type:String,
                default:"Welcome To DDHB ML"
            },

            buttonProps:{
                type:Object,
                require:true
            }
        }

    }
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .intro-block-description{
        width: 65%;
        min-height: 90%;
        margin: 16px 2%;

        padding:2px 16px;

        border: 2px #B0B0B0 solid;
        border-radius: 5px;

        background-color: #EBF5FB ;

        font-family: 'Noto Sans TC',sans-serif;

        overflow: auto;
        text-overflow: ellipsis;

        transition: 0.5s;
    }

    .leave-immediately{
        visibility: hidden;
        display:none;
    }

    h1{
        margin:16px auto;
        padding:0;
        font-weight: bold;
    }

</style>