<template>
<section>
  <header>
    <i class="iconfont icon-education"></i>
    <p>在校学习经历</p>
    <p>Education</p>
  </header>
  <article>
    <division class="sub-division" :left="studyingTime"></division>
    <section class="sub-university">{{ university }}</section>
    <section>
      <i class="iconfont icon-education"></i>
      <span>{{ major }}</span>
    </section>
    <dl>
      <dd v-for="item in experiences" :key="item.id">
        <i class="iconfont icon-file"></i>
        <span v-html="item"></span>
      </dd>
    </dl>
  </article>
</section>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import division from '@/components/division.vue';

@Component({
  components: {
    division,
  },
})
export default class Education extends Vue {
  private studyingTime = '2017 - 2021';
  private university = '中国矿业大学(211)';
  private major = '管理学院 | 电子商务系';
  private experiences: string[] = [
    '管理学院商务智能实验室 | 前端组成员',
    '熟悉MVMM框架<span>Vue.js</span>，进行多次项目开发',
    '熟悉JavaScript(含ES6)基本API, 了解使用TypeScript+vue进行开发',
    '熟悉html5语义标签，了解W3C标准,',
    '了解css及css3常用样式, 了解sass并运用scss进行样式开发，具有可读性',
    '了解微信小程序开发，有过单人项目经历',
    '了解Java后端流程，利用SpringBoot进行过简单接口开发',
    '了解Node.js事件驱动模型，运用Nest.js + MongoDB进行个人博客开发',
    '了解计算机网络七层架构及相应协议，了解HTTP工作原理',
  ]
  // private experienceSecond = '江苏省体育健康产业创新创业大赛 一等奖 | 线上产品设计';
}
</script>

<style lang="scss" scoped>
@media (min-width: 500px) {
  section {
    margin-top: 4rem;
    margin-bottom: 3rem;
    text-align: left;
    width: 90%;
    header {
      position: relative;
      left: 40px;
      i {
        font-size: 30px;
        color: white;
        background: #343434;
        padding: 8px;
        border-radius: 30px;
        float: left;
        margin-right: 1rem;
      }
      p {
        margin: .2rem;
      }
      p:nth-of-type(1) {
        font-size: 20px;
        font-weight: bold;
      }
      p:nth-of-type(2) {
        color: CadetBlue;
        font-size: 16px;
        font-weight: bolder;
      }
    }
    article {
      position: relative;
      border-left: 6px solid #343434;
      left: 60px;
      bottom: 5px;
      .sub-division {
        position: relative;
        top: .8rem;
      }
      .sub-university {
        margin: 1.4rem .8rem .8rem 1.9rem;
        font-size: 32px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      section, dd {
        margin: .5rem;
        margin-top: .8rem;
        i {
          font-size: 25px;
          margin-left: 1rem;
        }
        span {
          margin-left: 1rem;
          font-size: 18px;
          ::v-deep span{
            color: cadetblue;
            transition: all .5s;
          }
          ::v-deep span:hover {
            margin-right: .2rem;
            margin-left: .2rem;
          }
        }
      }
    }
    article:after {
      content: '';
      display: block;
      width: 20px;
      height: 20px;
      border-radius: 100%;
      background-color: #343434;
      position: relative;
      top: 1rem;
      left: -12px;
    }
  }
}
@media (max-width: 500px) {
  section {
    margin-top: 4rem;
    margin-bottom: 3rem;
    text-align: left;
    width: 90%;
    header {
      position: relative;
      left: 10px;
      i {
        font-size: 30px;
        color: white;
        background: #343434;
        padding: 8px;
        border-radius: 30px;
        float: left;
        margin-right: 1rem;
      }
      p {
        margin: .2rem;
      }
      p:nth-of-type(1) {
        font-size: 20px;
        font-weight: bold;
      }
      p:nth-of-type(2) {
        color: CadetBlue;
        font-size: 16px;
        font-weight: bolder;
      }
    }
    article {
      position: relative;
      border-left: 6px solid #343434;
      left: 30px;
      bottom: 5px;
      .sub-division {
        position: relative;
        top: .8rem;
      }
      .sub-university {
        margin: 1.4rem .8rem .8rem 1.9rem;
        font-size: 28px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      section, dd {
        margin: .5rem;
        margin-top: .8rem;
        i {
          font-size: 25px;
          margin-left: 1rem;
        }
        span {
          margin-left: 1rem;
          font-size: 18px;
          line-height: 1.8rem;
          ::v-deep span{
            color: cadetblue;
            transition: all .5s;
          }
          ::v-deep span:hover {
            margin-right: .2rem;
            margin-left: .2rem;
          }
        }
      }
    }
    article:after {
      content: '';
      display: block;
      width: 20px;
      height: 20px;
      border-radius: 100%;
      background-color: #343434;
      position: relative;
      top: 1rem;
      left: -12px;
    }
  }
}
</style>