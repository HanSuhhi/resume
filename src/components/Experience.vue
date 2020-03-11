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
      left: 'WebApp 鸵鸵搭大学生穿搭平台 （2020.1.10 - 至今）',
      header: '前端 | 部分后端及原型图绘制',
      player: '面向大学生的穿搭问答平台，为学生提供穿搭推荐、衣物收集、线下约游等服务，专业作业，拟参加三创赛',
      items: [
        '前端采用 Vue全家桶 + TypeScript 进行开发，使用高德地图提供地图功能，quillEditor提供富文本编辑器，阿里 OSS 提供图片存储功能',
        '开发早期，该项目为前端课大作业，并未搭建后端，导致实现购物车功能演示困难，其他组多采用假数据。通过vuex 状态管理以及将购物车信息保存成数组并转化为字符串，搭配设计相应算法，用纯前端实现店铺-购物车-订单的页面切换。',
        '开发时，后端返回的首页推送未包含推送图片参数，没有高度参数导致很难实现瀑布流布局。通过设置延时器，图片加载获取参数并进行瀑布流布局后再显示页面，实现瀑布流布局。缺点是如果请求数据过多，等待时间过长影响用户体验。项目后期后端修改接口解决该问题',
        '学习 git 分支管理，进行多人协作配合; 开发完成后通过UNIAPP跨端打包',
      ]
    },
    {
      left: 'web "生平区间"个人博客 （2020.2.13 - 至今）',
      header: '利用 NestJs 实现全栈开发',
      player: '个人博客，包括用户端、管理端、Node后端',
      items: [
        "用户端与管理端均采用 Vue + ts 进行开发, 使用 mavonEditor 实现 markdown语法 的编辑与展示，同时管理端使用 elementUI 进行设计",
        "后端采用 NestJs + MongoDB 进行开发, 使用 typegoose 辅助相应接口开发",
        "开发用户端时，页面底部想实现页面上划，内容从下往上展示类似于“手机锁屏上划解锁”效果。通过将页面底部属性设置为fixed并固定于页面底部，再将其他内容的z-index大于页面底部的z-index从而实现预期效果",
        "开发后端时，需要向用户端、管理端两个端口提供接口，并且两个端口共用的服务可以封装成一个模块。以数据库为例，通过封装一个数据库模块，用户端、管理端仅需导入数据库模块即可实现增删改查",
        "通过<span>媒体查询</span>实现简单自适应布局",
      ]
    },
    {
      left: "微信小程序 老王送水(2019.11.20 - 2019.12.04)",
      header: '前端 | 利用云开发处理数据',
      player: '为往返两个校区送水的送水校工王叔所作的小程序，希望通过小程序订单代替原本的电话订单，帮助王叔提高送水效率',
      items: [
        '使用微信小程序原生搭配云开发进行开发，通过小程序云函数处理订单信息，通过云数据库进行数据存储',
        '设计页面时，因为接单人与订水人共用一端，所有用户进入小程序后默认进入用户端，而接单人在“会员码”中输入给定密码，切换到管理端方可进行接单。而给出的UI设计图中，用户端与管理端的底部导航栏不完全相同，导致用户权限变化时，底部导航栏也需要进行相应变化。由于微信小程序给出的底部导航栏无法进行内容修改，通过禁用微信底部导航栏并设计一个风格类似的底部导航栏，利用数组驱动，从而当用户权限变化时，仅需对数组进行操作，即可完成需求',
        '通过<span>云函数</span>处理订单业务'
      ],
    },
    // {
    //   left: '简历制作',
    //   // right: '2020.3.2 - 2020.3.3',
    //   header: '简历制作',
    //   player: '',
    //   items: []
    // },
    // {
    //   left: "'疗动'体医融合康复平台",
    //   // right: '2019.11.30 - 2019.01.22',
    //   header: '团队项目 | 线上平台设计',
    //   player: '线上平台功能设计 | 原型图绘制',
    //   items: [
    //     '和其他成员设计平台功能，并进行可交互原型图的制作',
    //   ],
    // },
  ]
}
</script>
<style lang="scss" scoped>
@media (min-width: 768px) {
  section {
    margin-top: -.5rem;
      text-align: left;
    width: 95%;
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
      left: -12px;
    }
  }
}
@media (max-width: 768px) {
  section {
    margin-top: -.5rem;
    text-align: left;
    width: 95%;
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
      left: -12px;
    }
  }
}
</style>