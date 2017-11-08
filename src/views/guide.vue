<template>
    <div id="guide">
        <header>
            <div class="page-title"><span>新手指南</span></div>
        </header>
        <div style="height: 48px;"></div>

        <!--首页-->
        <div class="main_pho">
        <img class="main_pho_img" src="../../static/img/index.png">
        <!-- Swiper -->
        <div class="swiper-container">
            <div class="swiper-wrapper">
                <div class="swiper-slide">
                    <img src="../../static/img/index2.png">
                </div>
            </div>
            <!-- Add Scroll Bar -->
            <div style="opacity: 0;" class="swiper-scrollbar"></div>
        </div>
            <!--</div>-->
            <!--提示信息-->
            <div id="t1" class="t1" >向上滑动页面</div>
            <!--手势-->
            <div id="tu1" class="tu1" ><img src="../../static/img/shou.png"></div>

            <!--提示信息-->
            <div id="t2" class="t2" >点击选择心仪的商品</div>
            <!--跳转块-->
            <div id="box1" class="box1"></div>
            <!--手势-->
            <div id="tu2" class="tu2" ><img src="../../static/img/shou.png"></div>
        </div>

        <div class="main_part">
            <img src="../../static/img/particulars.png">
            <!--提示信息-->
            <div class="t2" id="t22" >在倒计时结束前出价</div>
            <!--跳转块-->
            <div class="box1" id="box2"></div>
            <!--手势-->
            <div class="tu2" id="tu22" ><img src="../../static/img/shou.png"></div>
        </div>
        <!--结束前往下一期-->
        <div class="main_over">
            <img src="../../static/img/over.png">
            <!--提示信息-->
            <div class="t2" id="t32" >竞拍结束可以前往下一期</div>
            <!--跳转块-->
            <div class="box1" id="box3"></div>
            <!--手势-->
            <div class="tu2" id="tu32" ><img src="../../static/img/shou.png"></div>
        </div>
        <!--个人中心-->
        <div class="main_own">
            <img src="../../static/img/own.png">
            <!--提示信息-->
            <div class="t2" id="t42" >前往个人中心查看我拍中</div>
            <!--跳转块-->
            <div class="box1" id="box4"></div>
            <!--手势-->
            <div class="tu2" id="tu42" ><img src="../../static/img/shou.png"></div>
        </div>

        <!--查看订单详情-->
        <div class="main_dan">
            <img src="../../static/img/dan.png">
            <!--提示信息-->
            <div class="t2" id="t52" >查看订单详情</div>
            <!--跳转块-->
            <div class="box1" id="box5"></div>
            <!--手势-->
            <div class="tu2" id="tu52" ><img src="../../static/img/shou.png"></div>
        </div>
        <!--拍中-->
        <div class="main_pai">
            <img src="../../static/img/pai.png">
            <!--提示信息-->
            <div class="t2" id="t62" >支付拍中价格</div>
            <!--跳转块-->
            <a href="#/find" class="box1" id="box6"></a>
            <!--手势-->
            <div class="tu2" id="tu62" ><img src="../../static/img/shou.png"></div>
        </div>
        <div class="prom">
            <p>向上滑动选择自己心仪的商品</p>
        </div>
        <div class="foot">
            <a href="javascript:location.reload();"><img src="../../static/img/back.png"></a>
            <p>新手指南（<span>1</span>/6）</p>
            <a class="prom_img"><img src="../../static/img/up.png"></a>
        </div>
    </div>
</template>
<script>
  export default {
    name: 'guide',
    components: {
    },
    data () {
      return {
      }
    },
     mounted (){
        var swiper = new Swiper('.swiper-container', {
            direction: 'vertical',
            slidesPerView: 'auto',
            mousewheelControl: true,
            freeMode: true,
            roundLengths : true, //防止文字模糊

        //滑动转点击选择商品
        onTouchMove: function(swiper){
            $("#tu1").css({
                "display":"none"
            });
            $("#t1").css({
                "display":"none"
            });
            $("#tu2").css({
                "display":"block"
            });
            $("#t2").css({
                "display":"block"
            });
            $("#box1").css({
                "display":"block"
            })
        }
        });

        $(function(){
    //    选择商品到商品详情
            $("#box1").click(function(){
                $(".main_pho").css({
                    "display":"none"
                });
                $(".main_part").css({
                    "display":"block"
                });
                $("#tu22").css({
                    "display":"block"
                });
                $("#t22").css({
                    "display":"block"
                });
                $("#box2").css({
                    "display":"block"
                });
                $(".foot p span").text(2);
                $(".prom p").text("设置出价数字，在倒计时结束前出价")
            });
            //    竞拍结束到下一期
            $("#box2").click(function(){
                $(".main_part").css({
                    "display":"none"
                });
                $(".main_over").css({
                    "display":"block"
                });
                $("#tu32").css({
                    "display":"block"
                });
                $("#t32").css({
                    "display":"block"
                });
                $("#box3").css({
                    "display":"block"
                });
                $(".foot p span").text(3);
                $(".prom p").text("竞拍结束可以前往下一期")
            });
            //    前往个人中心
            $("#box3").click(function(){
                $(".main_over").css({
                    "display":"none"
                });
                $(".main_own").css({
                    "display":"block"
                });
                $("#tu42").css({
                    "display":"block"
                });
                $("#t42").css({
                    "display":"block"
                });
                $("#box4").css({
                    "display":"block"
                });
                $(".foot p span").text(4);
                $(".prom p").text("前往个人中心查看我拍中")
            });
            //    查看订单详情
            $("#box4").click(function(){
                $(".main_own").css({
                    "display":"none"
                });
                $(".main_dan").css({
                    "display":"block"
                });
                $("#tu52").css({
                    "display":"block"
                });
                $("#t52").css({
                    "display":"block"
                });
                $("#box5").css({
                    "display":"block"
                });
                $(".foot p span").text(5);
                $(".prom p").text("点击查看订单详情")
            });
            //   支付拍中的商品
            $("#box5").click(function(){
                $(".main_dan").css({
                    "display":"none"
                });
                $(".main_pai").css({
                    "display":"block"
                });
                $("#tu62").css({
                    "display":"block"
                });
                $("#t62").css({
                    "display":"block"
                });
                $("#box6").css({
                    "display":"block"
                });
                $(".foot p span").text(6);
                $(".prom p").text("支付拍中的商品")
            });
            //        提示信息
            var current = 0;
            $(".foot .prom_img").click(function(){
                current = (current+180)%360;
                $(".foot .prom_img").css({
                "transform":'rotate('+current+'deg)'
            });
                $(" .prom").slideToggle();
            });

        });
    }
  }
</script>

<style>
    .page-title {
        height: 48px;
        line-height: 48px;
        text-align: center;
        color: #fff;
        background-color: #ef4d45;
        font-size: 18px;
        font-weight: 700;
        position: fixed;
        width: 100%;
        z-index: 2;
    }
    /*底部*/
    .mint-tabbar.is-fixed {
        right: 0;
        bottom: 0;
        left: 0;
        position: fixed;
        z-index: 1;
    }

    .mint-tabbar[data-v-9fc91b0c] {
        border-top: 1px solid #ebebeb;
        background-color: #fff;
        color: #999;
    }
    .mint-tabbar.is-fixed {
        z-index: 4!important;
    }
    .mint-tabbar {
        background-image: linear-gradient(180deg,#d9d9d9,#d9d9d9 50%,transparent 0);
        background-size: 100% 1px;
        background-repeat: no-repeat;
        background-position: 0 0;
        position: relative;
        background-color: #fafafa;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        right: 0;
        bottom: 0;
        left: 0;
        position: absolute;
        text-align: center;
    }
    /*底a*/
    .mint-tabbar>.mint-tab-item.is-selected[data-v-9fc91b0c] {
        color: #ef4d45;
        background-color: transparent;
    }
    .mint-tabbar>.mint-tab-item.is-selected {
        background-color: #eaeaea;
        color: #26a2ff;
    }

    .mint-tab-item[data-v-9fc91b0c] {
        padding: 5px 0;
    }
    .mint-tab-item {
        display: block;
        padding: 7px 0;
        -webkit-box-flex: 1;
        -ms-flex: 1;
        flex: 1;
        text-decoration: none;
    }
    a {
        text-decoration: none;
        -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    }
    /*图片*/
    .mint-tab-item-icon {
        width: 24px;
        height: 24px;
        margin: 0 auto 5px;
    }
    /*图片i*/
    .icon-tabbar.icon-home.active[data-v-9fc91b0c] {
        background-position: -1px -38px;
    }
    .icon-tabbar.icon-home[data-v-9fc91b0c] {
        background-position: 0 1px;
    }
    .icon-tabbar[data-v-9fc91b0c] {
        background: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zd…Q0LDAsMCwwLDIsMEwxMTcsNzkuNDJsMi4xNC0yLjE0WiIvPjwvZz48L2c+PC9nPjwvc3ZnPg==) no-repeat;
        background-size: 236px;
    }
    .mint-tab-item-icon>* {
        display: block;
        width: 100%;
        height: 100%;
    }
    /*文字*/
    .mint-tab-item-label {
        color: inherit;
        font-size: 12px;
        line-height: 1;
    }

    html, body {position: relative;height: 100%}
    #guide {background: #fff;font-family: Helvetica Neue, Helvetica, Arial, sans-serif;font-size: 14px;color:#000; margin: 0;padding: 0;}
    .prom{position: absolute;bottom: 40px;border-top: 1px #f6f6f6 solid;width: 90%;height: 30px;padding: 0 5%;display: block;}
    .prom p{line-height: 30px;margin: 0;font-size: 12px;}
    .foot{position: absolute;bottom: 0;border-top: 1px #f6f6f6 solid;width: 100%;height: 40px;display: inline-block;}
    .foot p{width: 70%;margin: 0 auto;line-height: 40px;text-align: center;display: inline-block;float: left;}
    .foot p span{color: #ef4d45;}
    .foot a{    width: 15%;
        display: block;
        height: 40px;
        line-height: 50px;
        float: left;}
    .foot a img{width: 40%;margin-left: 30%;}
    .main_pho{width: 200px;position: absolute; margin: 0px auto; top: 40%; margin-top: -209px; left: 50%;margin-left: -100px;}
    .main_pho .main_pho_img{ width: 100%;}
    .swiper-container {width: 179px;height: 281px;position: absolute; top: 58px;left: 11px; overflow: hidden;}
    .swiper-slide {width: 179px;height: auto;}
    .swiper-slide img{ width: 100%;}

    .tu1{width:60px;position:absolute;top: 280px;right: -20px; animation:ghostUpdown 1s infinite alternate; -webkit-animation:ghostUpdown 1s infinite alternate; z-index: 2;}
    @keyframes ghostUpdown{
        from{margin-top:0;}
        to{margin-top:-50px;}
    }
    @-webkit-keyframes ghostUpdown{
        from{margin-top:0;}
        to{margin-top:-50px;}
    }
    .tu2{width:60px;position:absolute;top: 280px;right: -20px; animation:ghostUpdown1 1s infinite alternate; -webkit-animation:ghostUpdown1 1s infinite alternate; z-index: 2;display: none}
    @keyframes ghostUpdown1{
        from{margin-right:20px;}
        to{margin-right:0;}
    }
    @-webkit-keyframes ghostUpdown1{
        from{margin-right:20px;}
        to{margin-right:0;}
    }
    .tu1 img,.tu2 img{width: 100%;transform:rotate(240deg);
        -ms-transform:rotate(240deg); /* IE 9 */
        -webkit-transform:rotate(240deg); /* Safari and Chrome */
    }

    .yy{background-size: 100%;}
    .t1,.t2{background: url("../../static/img/yuan.png") no-repeat;background-size: 100%;width: 80px;height: 50px;position: absolute;top: 200px;left: 50px;z-index: 2;color: #ef4d45;font-size: 14px;text-align: center;font-weight: bold}
    .t2{display: none;}
    .box1{width: 80px;height: 50px;position: absolute;top: 260px;right: 10px;z-index: 3;display: none;}

    /*商品详情*/
    .main_part,.main_over,.main_own,.main_dan,.main_pai{width: 200px;position: absolute; margin: 20px auto;display: none;top: 40%; margin-top: -209px; left: 50%;margin-left: -100px;}
    .main_part img, .main_over img, .main_own img, .main_dan img, .main_pai img{ width: 100%;}
    #t22,#t32{top: 260px;left: 150px; }
    #box2, #box3{top: 320px;right: 10px;}
    #box3{width: 180px;}
    #tu22,#tu32{top: 350px;right: -30px;}
    #t42{top: 160px;left: 60px; }
    #box4{top: 220px;right: 60px;}
    #tu42{top: 235px; right: 35px;}
    #t52{top: 190px;left: 100px; }
    #box5{top: 115px;right: -10px;}
    #tu52{top: 140px; right: -20px;}
    #t62{top: 160px;left: 70px; }
    #box6{top: 100px;right: 0;}
    #tu62{top: 125px; right: -25px;}

</style>