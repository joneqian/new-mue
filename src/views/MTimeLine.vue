<template>
  <div class="timeline-demo">
    <timeline>
      <timeline-item>
        <h4 class="recent">【广东】 广州市 已发出</h4>
        <p class="recent">2016-04-17 12:00:00</p>
      </timeline-item>
      <timeline-item>
        <h4> 申通快递员 广东广州 收件员 xxx 已揽件</h4>
        <p>2016-04-16 10:23:00</p>
      </timeline-item>
      <timeline-item>
        <h4> 商家正在通知快递公司揽件</h4>
        <p>2016-04-15 9:00:00</p>
      </timeline-item>
    </timeline>
    <timeline>
      <timeline-item v-for="(i, index) in count" :key="index">
        <h4 :class="[i === 0 ? 'recent' : '']">Timeline Node {{i + 1}}</h4>
        <p :class="[i === 0 ? 'recent' : '']">index {{i + 1}}</p>
      </timeline-item>
    </timeline>

    <m-button type="primary" @click.native="count = 6"> Set to 6 nodes</m-button>
    <m-button type="primary" @click.native="count = 3"> Set to 3 nodes</m-button>
  </div>
</template>

<script>
  import Timeline from '../components/timeline/timeline.vue';
  import TimelineItem from '../components/timeline/timeline-item.vue';
  import MButton from '../components/m-button/index';

  export default {
    components: {
      Timeline,
      TimelineItem,
      MButton
    },
    data () {
      return {
        count: 3
      };
    }
  };
</script>

<style lang="less">
  .timeline-demo {
   padding:.24rem;
    p {
      color: #999;
      font-size: 0.22rem;
    }
    h4 {
      color: #666;
      font-weight: normal;
      font-size: .26rem;
    }
    .recent {
      color: rgb(255, 186, 0)
    }
  }
</style>
