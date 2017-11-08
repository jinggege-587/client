<template>
    <div id="share">
        <header>
            <div class="page-title"><span>晒分享</span></div>
        </header>
        <div style="height: 48px;"></div>
        <div class="mint-find">
            <mt-cell title="晒单分享" to="//github.com" is-link value="带链接"></mt-cell>
            <mt-cell title="晒单分享" to="//github.com" is-link value="带链接"></mt-cell>
            <mt-cell title="新手引导"></mt-cell>
            <mt-cell title="标题文字" value="说明文字"></mt-cell>

        </div>
    </div>
</template>

<script>
  export default {
    name: 'share',
    components: {
    },
    data () {
      return {
      }
    }
  }
</script>
<style>
    .mint-find ul,.mint-find li{padding: 0px;margin: 0px;}
    .mint-cell{
        border-bottom: 1px solid #eaeaea;
    }
    
</style>
