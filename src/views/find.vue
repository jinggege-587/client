<template>
    <div id="find" style="background:#f6f6f6;">
        <header>
            <div class="page-title"><span>发现</span></div>
        </header>
        <div style="height: 48px;"></div>
        <div class="mint-find">
            <ul>
                <li>
                <a href="#/share">
                    <div class="mint-find-cen">
                        <div class="mint-find_img">
                            <div style="background: #ef4d45;width:64px;height: 64px;border-radius: 32px;"></div>
                        </div>
                        <div class="mint-find_nei">
                            <h5>晒单分享<b>hot</b></h5>
                            <p>快来看看都有谁拍中了~</p>
                        </div>
                    </div>
                </a>
                </li>
                <li>
                    <a href="#/guide">
                        <div class="mint-find-cen">
                            <div class="mint-find_img">
                                <img src="../../static/img/fa_ac.png">
                                <!--<div style="background: #ef0000;width:64px;height: 64px;border-radius: 32px;"></div>-->
                            </div>
                            <div class="mint-find_nei">
                                <h5>新手指南<b>yoo</b></h5>
                                <p>先来了解下怎么玩儿吧~</p>
                            </div>
                        </div>
                    </a>
                </li>


            </ul>

        </div>
        <footer>
            <div data-v-9fc91b0c="" class="mint-tabbar is-fixed">
                <a data-v-9fc91b0c="" class="mint-tab-item page-tabbar-item">
                    <div class="mint-tab-item-icon"><i data-v-9fc91b0c="" class="icon-tabbar icon-home"></i></div>
                    <div class="mint-tab-item-label"> 主页</div>
                </a>
                <a data-v-9fc91b0c="" class="mint-tab-item page-tabbar-item">
                    <div class="mint-tab-item-icon"><i data-v-9fc91b0c="" class="icon-tabbar icon-pai"></i></div>
                    <div class="mint-tab-item-label"> 最新成交</div>
                </a>
                <a data-v-9fc91b0c="" class="mint-tab-item page-tabbar-item is-selected">
                    <div class="mint-tab-item-icon"><i data-v-9fc91b0c="" class="icon-tabbar icon-fa active"></i></div>
                    <div class="mint-tab-item-label"> 发现</div>
                </a>
                <a data-v-9fc91b0c="" class="mint-tab-item page-tabbar-item">
                    <div class="mint-tab-item-icon"><i data-v-9fc91b0c="" class="icon-tabbar icon-allpai"></i></div>
                    <div class="mint-tab-item-label"> 全部商品 </div>
                </a>
                <a data-v-9fc91b0c="" class="mint-tab-item page-tabbar-item">
                    <div class="mint-tab-item-icon"><i data-v-9fc91b0c="" class="icon-tabbar icon-user"></i></div>
                    <div class="mint-tab-item-label"> 个人中心</div>
                </a>
            </div>
        </footer>
    </div>
</template>

<script>
  export default {
    name: 'find',
    components: {
    },
    data () {
      return {
      }
    }
  }
</script>

<style>
    *{margin: 0;padding: 0;}
    /*加发现*/
    .is-selected .icon-fa.active{
        background: url("../../static/img/fa_ac.png") no-repeat;background-size: 100%;
    }
    .is-selected .icon-fa{
        background: url("../../static/img/fa.png") no-repeat;background-size: 100%;
    }

    .mint-find ul li{
        margin-top: 10px;;
    }
    .mint-find a{
        display: block;
        padding: 5px 10px;
        background: #fff;
    }
    .mint-find-cen{
        position: relative;
    }
    .mint-find_img{
        display: inline-block;
        width: 64px;
        height: 64px;
        border-radius: 40px;
    }
    .mint-find_img img{
        width: 100%;
        border-radius: 50%;

    }
    .mint-find_nei{
        display: inline-block;
        position: absolute;
        top: 14px;
        left: 74px;
    }
    .mint-find_nei h5{
        line-height: 20px;
        font-size: 16px;
    }
    .mint-find_nei h5 b{
        background: #ef4d45;
        display: inline-block;
        border-radius: 8px;
        line-height: 10px;
        font-size: 13px;;
        font-weight: lighter;
        padding: 3px;
        margin-left: 5px;
        color: #fff;
    }
    .mint-find_nei p{
        line-height: 20px;
        font-size: 14px;
    }
    .maina-fine_nei p {


    }
    .mint-find-cen:after {
    border: 2px solid #c8c8cd;
    border-bottom-width: 0;
    border-left-width: 0;
    content: " ";
    top: 50%;
    right: 0;
    position: absolute;
    width: 10px;
    height: 10px;
    -webkit-transform: translateY(-50%) rotate(45deg);
    transform: translateY(-50%) rotate(45deg);
    }
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


</style>