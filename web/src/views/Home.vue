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

    <m-list-card icon="Menu" title="新闻资讯" :categories="newsCats">
      <template #items="{category}">
        <div class="py-2" v-for="(news, i) in category.newsList" :key="i">
          <span>[{{news.categoryName}}]</span>
          <span>|</span>
          <span>{{news.title}}</span>
          <span>{{news.date}}</span>
        </div>
      </template>
    </m-list-card>
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
      },
      newsCats: [
        {
          name: '热门',
          newsList: new Array(5).fill({}).map(() => (
            {
              categoryName: '公告',
              title: '6月2日全服不停机更新公告',
              date: '06/01'
            }
          ))
        },
        {
          name: '新闻',
          newsList: new Array(5).fill({}).map(() => (
            {
              categoryName: '新闻',
              title: '6月2日全服不停机更新公告',
              date: '06/01'
            }
          ))
        },
        {
          name: '新闻',
          newsList: new Array(5).fill({}).map(() => (
            {
              categoryName: '新闻',
              title: '6月2日全服不停机更新公告',
              date: '06/01'
            }
          ))
        },
        {
          name: '新闻',
          newsList: new Array(5).fill({}).map(() => (
            {
              categoryName: '新闻',
              title: '6月2日全服不停机更新公告',
              date: '06/01'
            }
          ))
        },
        {
          name: '新闻',
          newsList: new Array(5).fill({}).map(() => (
            {
              categoryName: '新闻',
              title: '6月2日全服不停机更新公告',
              date: '06/01'
            }
          ))
        }
      ]
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
