<template>
  <div class="message">
    <div class="page-wrap">
      <div class="page-title">
        <a @click="routerBack">
          <i class="icon-back"></i>
        </a>
        <span>公告消息</span>
      </div>
      <div class="page-content">
        <div class="media-list">
          <router-link :to="{name: 'messageList', query: {type: 'system'}}" class="media-item">
            <div class="media-img">
              <img src="static/icon/icon-item-bell.svg" alt="">
            </div>
            <div class="media-title">
              <h5>系统公告
                <!-- <span>2017-07-27</span> -->
              </h5>
              <!-- <p>关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告</p> -->
              <div class="circle-red"></div>
            </div>
          </router-link>
          <router-link :to="{name: 'messageList', query: {type: 'personal'}}" class="media-item">
            <div class="media-img">
              <img src="static/icon/icon-item-paper.svg" alt="">
            </div>
            <div class="media-title">
              <h5>个人通知
                <!-- <span>2017-07-27</span> -->
              </h5>
              <!-- <p>关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告关于发货时间调整的公告</p> -->
              <div class="circle-red"></div>
            </div>
          </router-link>
          <!-- <router-link :to="{name: 'messageInfo'}" class="media-item">
            <div class="media-img">
              <img src="static/icon/icon-item-paper.svg" alt="">
            </div>
            <div class="media-title">
              <h5>拍币说明
                <span>2017-07-27</span>
              </h5>
              <p>关于充值拍币后不可退回的说明</p>
              <div class="circle-red"></div>
            </div>
          </router-link> -->
        </div>
        <!-- <div class="media-list">
          <router-link :to="{name: 'messageInfo'}" class="media-item">
            <div class="media-img">
              <img src="static/icon/icon-item-gift.svg" alt="">
            </div>
            <div class="media-title">
              <h5>中奖消息</h5>
              <p>恭喜你中得iPhone 7s Plus 一部，请尽快下单。</p>
              <div class="circle-red"></div>
            </div>
          </router-link>
          <router-link :to="{name: 'messageInfo'}" class="media-item">
            <div class="media-img">
              <img src="static/icon/icon-item-car.svg" alt="">
            </div>
            <div class="media-title">
              <h5>发货消息</h5>
              <p>您拍中的商品正搭快车赶往您身边</p>
              <div class="circle-red"></div>
            </div>
          </router-link>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'message',
  data () {
    return {
    }
  },
  methods: {
    routerBack () {
      this.$router.go(-1)
    }
  }
}
</script>

<style>
.media-list {
  width: 100%;
  padding: 0;
  margin-bottom: 10px;
  border-top: 1px solid #f2f2f2;
}

a.media-item {
  display: inline-block;
  margin: 0 0 -4px 0;
  padding: 0;
  width: 100%;
  position: relative;
  border-bottom: 1px solid #f2f2f2;
  background-color: #FFFFFF;
}

a.media-item .media-img {
  width: 15%;
  float: left;
}

a.media-item .media-img img {
  margin: 10px 0 5px 10px;
  min-width: 24px;
  max-width: 56px;
}

.media-title {
  width: 85%;
  float: left;
}

.media-title h5 {
  padding: 14px 10px 5px 10px;
  font-size: 14px;
  font-weight: 500;
  color: #333333;
}

.media-title p {
  padding: 0 30px 10px 10px;
  white-space: nowrap;
  word-wrap: normal;
  text-overflow: ellipsis;
  overflow: hidden;
  font-size: 12px;
  color: #999999;
}

.media-title span {
  float: right;
  font-weight: 300;
  font-size: 12px;
  color: #999999;
  vertical-align: middle;
}

div.circle-red {
  width: 10px;
  height: 10px;
  border-radius: 30px;
  background-color: #ef0000;
  position: absolute;
  right: 10px;
  top: 38px;
}
</style>
