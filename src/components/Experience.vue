<template>
<section>
  <header>
    <i class="iconfont icon-project"></i>
    <p>项目经历</p>
    <p>Experiences</p>
  </header>
  <article>
    <experience-item
      class="experience-item"
      v-for="item in AllExperiences"
      :key="item.id"
      :experienceDetails="item">
    </experience-item>
  </article>
</section>
</template>
<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import ExperienceItem from '@/components/experience-item.vue';
import { ExperienceDetail } from '@/common/experience-detail';

@Component({
  components: {
    ExperienceItem,
  },
})
export default class Experience extends Vue {
  private AllExperiences: Array<ExperienceDetail> = [
    {
      left: '鸵鸵搭大学生穿搭平台',
      // right: '2019.12.11 - 2020.2.10',
      header: 'CDIO 小组项目 | 从理念至上线全程参与',
      player: '原型图制作 | 前端 | 后端',
      items: [
        "<a href='http://www.shengpingqj.com' target='blank'>www.shengpingqj.com</a> 请使用移动端查看",
        "<a href='https://github.com/HanSuhhi/tuotuoda_Java' target='blank'>https://github.com/HanSuhhi/tuotuoda_Java</a>  后端源码地址",
        "<a href='https://github.com/HanSuhhi/tuotuoda_ts' target='blank'>https://github.com/HanSuhhi/tuotuoda_ts</a> 前端源码地址",
        '后端采用 SSM 框架，前端采用 Vue + ts 开发',
        '首页根据个人理解实现瀑布流推送',
        '学习 git 分支管理，尝试多人协作配合',
        '使用 Axure 设计制作可交互原型图，使用 Visio 制作部分系统流程图',
      ]
    },
    {
      left: '生平区间 个人博客',
      // right: '2020.2.13 - 目前',
      header: '个人学习项目',
      player: '前端用户端 | 前端管理端 | Node后端',
      items: [
        "<i>因为小组作业需要，博客域名内容暂时替换为穿搭平台</i>",
        "<a href='https://github.com/HanSuhhi/blogHttp' target='blank'>https://github.com/HanSuhhi/blogHttp</a>  用户端地址",
        "<a href='https://github.com/HanSuhhi/blog_admin' target='blank'>https://github.com/HanSuhhi/blog_admin</a>  管理端源码",
        "<a href='https://github.com/HanSuhhi/blog_server' target='blank'>https://github.com/HanSuhhi/blog_server</a>  后端源码",
        "用户端为锻炼切图设计能力，未采用 UI 框架，目前实现简单自适应",
        "管理端采用 ElementUI，学习相应 UI 框架使用",
        "后端采用NestJs + MongoDB, 学习模块化思维，已组装 database 模块",
        "加深学习 Node，力争改变自己对Node的不求甚解"
      ]
    },
    {
      left: "'老王送水' 微信小程序",
      // right: '2019.11.20 - 2019.12.04',
      header: '实验室项目 | 在部分页面完成后接手',
      player: '云开发 | 中后期个人开发',
      items: [
        "<a href='https://github.com/HanSuhhi/laoWangWater' target='blank'>https://github.com/HanSuhhi/laoWangWater</a> 微信小程序源码",
        '项目开发未注意权限，审核因个人开发者权限问题而搁置，正在解决中',
        '开发送水员页面，结合前期小组成员完成的普通用户界面，通过密码切换身份',
        '通过云函数处理订单业务'
      ],
    },
    // {
    //   left: '简历',
    //   right: '2020.3.2 - 2020.3.3',
    //   header: '',
    //   player: '',
    //   items: []
    // },
    {
      left: "'疗动'体医融合康复策略",
      // right: '2019.11.30 - 2019.01.22',
      header: '团队项目 | 负责线上平台设计搭建',
      player: '线上平台功能设计 | 原型图绘制',
      items: [
        '和其他成员设计制作可交互原型图',
      ],
    },
  ]
}
</script>
<style lang="scss" scoped>
@media (min-width: 500px) {
  section {
    margin-bottom: 1rem;
    text-align: left;
    width: 93%;
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
      border-left: 6px solid #343434;
      position: relative;
      left: 60px;
      top: -.9rem;
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
    margin-bottom: .5rem;
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
      border-left: 6px solid #343434;
      position: relative;
      left: 30px;
      top: -.9rem;
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