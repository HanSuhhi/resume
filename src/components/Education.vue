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
    <section class="major">
      <i class="iconfont icon-education"></i>
      <span>{{ major }}</span>
    </section>
    <dl>
      <!-- P1 -->
      <dd v-for="item in experiences" :key="item.id">
        <i class="iconfont icon-file"></i>
        <span v-html="item"></span>
      </dd>
      <!-- P2 -->
      <dd>
        <h3 style="margin: 1rem .3rem;margin-left: 17px">技术能力</h3>
      </dd>
      <dd v-for="item in skills" :key="item.id" style="margin-left: 27px;font-size: 14px;">
        <span v-html="item"></span>
      </dd>
      <!-- p3 -->
      <dd>
        <h3 style="margin: 1rem .3rem;margin-left: 17px">学生工作经验</h3>
      </dd>
      <dd v-for="item in department" :key="item.id">
        <div v-html="item" style="margin-left: 17px; font-size: 14px"></div>
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
    '<b>实验室</b>： 管理学院商务智能实验室 | 前端组成员 ：参与多项实验室项目（前端）',
    '<b>大创工作室</b>： i++工作室前端组组长，与其他组协同参与项目开发，已上线小程序一款',
    '<b>相关课程</b>： 电子商务编程基础 <b>87</b> 、Web前端高级开发技术 <b>90</b> 、辅修计算机核心课程（高级语言程序设计、数据结构、计算机网络等）',
    '<b>获奖经历</b>：“赢在徐州”跨境电商创业赛高校组一等奖 组长 <b>2018</b> | 第四届江苏省大学生体育健康产业创新创业大赛一等奖 线上产品 <b>2019</b>',
  ]
  private department: string[] = [
    '<h3 style="font-size: 16px;letter-spacing: 1px;margin: .3rem">2017.10 - 2018.07 校宣传部干事</h3>',
    '<li style="margin-left: 10px">做事积极： 完成微信推文30余篇，远超基本要求15篇</li>',
    '<h3 style="font-size: 16px;letter-spacing: 1px;margin: .3rem">2018.09 - 2019.09 之江学社宣传部部长</h3>',
    '<li style="margin-left: 10px">工作负责： 创立部门公众号、部员排版培训、构思创意主题3个、制作推文10余篇</li>',
    '<li style="margin-left: 10px">性格外向： 随书记拜访市浙江商会，与对方宣传部门现场配合，当晚新闻见报</li>',
  ];
  private skills: string[] = [
    '<i class="iconfont icon-file" style="margin-right: 1rem;font-size: 14px;margin-left: -20px;"></i><b>掌握前端基础能力</b>',
    '熟悉前端开发语言：HTML、CSS(含 Sass )、JavaScript (含 ES6 )及基本 API 使用, 了解并使用<span> TypeScript </span>进行项目开发',
    '<i class="iconfont icon-file" style="margin-right: 1rem;font-size: 14px;margin-left: -20px;"></i><b>有移动 Web 开发能力</b>',
    '熟悉 MVVM 框架<span> Vue.js </span>及相关技术栈：axios、vuex等，了解常用模块化工具 Webpack， 了解 git 基本操作',
    '根据自我理解实现瀑布流，实现首页推送瀑布流',
    '<i class="iconfont icon-file" style="margin-right: 1rem;font-size: 14px;margin-left: -20px;"></i><b>有 Nodejs 开发能力</b>',
    '熟悉 MVC, 了解<span> Node.js </span>事件驱动模型，运用 Nest.js + MongoDB 进行过个人博客开发',
    '了解 Java 后端开发，利用 SSM 框架进行过后台开发',
    '<i class="iconfont icon-file" style="margin-right: 1rem;font-size: 14px;margin-left: -20px;"></i><b>有小程序开发能力</b>',
    '了解微信小程序开发，有个人小程序及合作开发小程序经历，了解相关标签及使用',
    '<i class="iconfont icon-file" style="margin-right: 1rem;font-size: 14px;margin-left: -20px;"></i><b>一定计算机网络知识</b>',
    '了解计算机网络七层架构及相应协议，了解 HTTP 工作原理',
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
        font-size: 14px;
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
        margin: 1.4rem .8rem .8rem 1rem;
        font-size: 22px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      dd {
        margin: .5rem;
        margin-top: .6rem;
        i {
          font-size: 14px;
          margin-left: 1rem;
        }
        span {
          margin-left: 1rem;
          font-size: 14px;
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
          ::v-deep div {
            h2, h3 {
              margin: 0px;
            }
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
        margin: 1.4rem .8rem .8rem 1rem;
        font-size: 22px;
        font-weight: bolder;
        letter-spacing: 2px;
      }
      dd {
        margin: .5rem;
        margin-top: .2rem;
        i {
          font-size: 14px;
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
          ::v-deep div {
            ::v-deep h2, ::v-deep h3 {
              margin: 0px;
            }
          }
        }
      }
      section {
        margin: .5rem;
        margin-top: .2rem;
        i {
          font-size: 14px;
          margin-left: 1rem;
        }
        span {
          margin-left: .5rem;
          font-size: 14px;
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