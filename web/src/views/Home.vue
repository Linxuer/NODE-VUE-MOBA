<template>
  <div>
    <swiper ref="mySwiper" :options="swiperOption">
      <swiper-slide>
        <img class="w-100" src="../assets/images/1.png" height="200">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/2.png" height="200">
      </swiper-slide>
      <swiper-slide>
        <img class="w-100" src="../assets/images/3.png" height="200">
      </swiper-slide>
      <div class="swiper-pagination pagination-home text-right px-3 pb-1" slot="pagination"></div>
    </swiper>
    <!-- end of swiper -->

    <div class="nav-icons bg-white mt-3 text-center pt-3 text-dark-1">
      <div class="d-flex flex-wrap">
        <div class="nav-item mb-3" v-for="n in 10" :key="n">
          <i class="sprite sprite-news"></i>
          <div class="py-2">爆料站</div>
        </div>
      </div>
      <div class="bg-light py-2 fs-sm">
        <i class="sprite sprite-arrow mr-1"></i>
        <span>收起</span>
      </div>
    </div>
    <!-- end of nav icon -->

    <m-card icon="Menu" title="新闻咨询">
      <div class="nav jc-between">
        <div class="nav-item active">
          <div class="nav-link">热门</div>
        </div>
        <div class="nav-item">
          <div class="nav-link">新闻</div>
        </div>
        <div class="nav-item">
          <div class="nav-link">新闻</div>
        </div>
        <div class="nav-item">
          <div class="nav-link">新闻</div>
        </div>
        <div class="nav-item">
          <div class="nav-link">新闻</div>
        </div>
      </div>

      <div class="pt-3">
        <swiper>
          <swiper-slide v-for="n in 5" :key="n">
            <div class="p-2" v-for="n in 5" :key="n">
              <span>[新闻]</span>
              <span>|</span>
              <span>很多新闻很多新闻很多新闻很多新闻很多</span>
              <span>06/02</span>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </m-card>
    <m-card icon="Menu" title="英雄列表"></m-card>
    <m-card icon="Menu" title="精彩视频"></m-card>
    <m-card icon="Menu" title="图文攻略"></m-card>
    <m-card icon="Menu" title="英雄列表"></m-card>
    <m-card icon="Menu" title="英雄列表"></m-card>
  </div>
</template>

<script>

export default {
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.pagination-home',
        },
      }
    }
  },

  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper
    }
  },

  mounted () {
    console.log('Current Swiper instance object', this.swiper)
    this.swiper.slideTo(3, 1000, false)
  },

  methods: {

  }
}
</script>

<style lang="scss">
@import '../assets/scss/variables';

.pagination-home {
  .swiper-pagination-bullet {
    opacity: 1;
    border-radius: .153846rem;
    background: map-get($colors, 'white');
    &.swiper-pagination-bullet-active {
      background: map-get($colors, 'info');
    }
  }
}

.nav-icons {
  border-top: 1px solid $border-color;
  border-bottom: 1px solid $border-color;
  .nav-item {
    width: 25%;
    border-right: 1px solid $border-color;
    &:nth-child(4n) {
      border-right: none;
    }
  }
}
</style>
