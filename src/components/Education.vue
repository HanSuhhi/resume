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
    '管理学院商务智能实验室 | 前端组成员 | 参与多项实验室项目，帮助其他组员解决相关开发问题',
    '熟悉 MVMM 框架<span> Vue.js </span>，并进行多次项目开发，了解router、axios、vuex等相关组件使用',
    '熟悉 JavaScript (含 ES6 )及基本 API 使用, 了解使用<span> TypeScript </span> + vue 进行项目开发',
    '熟悉 JavaScript 中 this 指针、异步编程、promise 等相关内容',
    '熟悉 html5 语义标签，了解 W3C 标准,利用语义标签、flex布局等实现较为复杂的页面布局',
    '了解 css常用样式, 了解 sass 并运用 scss 进行样式开发，代码具有可读性，可以制作简单的动画设计',
    '了解微信小程序开发，有过单人云开发项目经历，了解相关标签及其使用',
    '了解 Java 后端开发，有利用 SSM 框架进行后台开发，前后端联调测试经历及相关项目',
    '了解<span> Node.js </span>事件驱动模型，运用 Nest.js + MongoDB 进行个人博客开发， 了解 Node 模块化',
    '了解计算机网络七层架构及相应协议，了解 HTTP 工作原理, 了解 git 基本操作',
  ]
}
</script>

<style lang="scss" scoped>
@media (min-width: 768px) {
  section {
    margin-top: 1.5rem;
    margin-bottom: 1rem;
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
        font-size: 22px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      dd {
        margin: .5rem;
        margin-top: .6rem;
        i {
          font-size: 16px;
          margin-left: 1rem;
        }
        span {
          margin-left: 1rem;
          font-size: 16px;
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
      section {
        margin: .5rem;
        margin-bottom: 0;
        i {
          font-size: 18px;
          margin-left: 1rem;
        }
        span {
          font-weight: bold;
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
      left: -12px;
    }
  }
}
@media (max-width: 768px) {
  section {
    margin-top: 1rem;
    margin-bottom: 1rem;
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
        font-size: 22px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      dd {
        margin: .5rem;
        margin-top: .2rem;
        i {
          font-size: 16px;
          margin-left: 1rem;
        }
        span {
          margin-left: .5rem;
          font-size: 14px;
          line-height: .2rem;
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
      section {
        margin: .5rem;
        margin-top: .2rem;
        i {
          font-size: 16px;
          margin-left: 1rem;
        }
        span {
          margin-left: .5rem;
          font-size: 16px;
          font-weight: bold;
          line-height: .2rem;
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
      left: -12px;
    }
  }
}
</style>