<template>
  <div>
    <page-header title="欢迎使用「智慧城管综合管理系统」">
      <template #content>
      </template>
    </page-header>
    <page-main>
      <el-row :gutter="24" v-show="isAdmin">
        <el-col :span="6" :offset="0">
          <Card
            title="/rq-manager/info"
            num="城市管理"
            tip="管理城市信息"
            type="green"
            icon="el-icon-office-building"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/building-manager/building"
            num="楼宇管理"
            tip="所有楼宇详细记录"
            type="green"
            icon="el-icon-school"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/building-manager/room"
            num="房间管理"
            tip="楼盘内房间管理"
            type="pink"
            icon="el-icon-house"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/rq-manager/facilities"
            num="公共设施"
            tip="城市内所有公共设施"
            type="pink"
            icon="el-icon-chat-square"
          />
        </el-col>
      </el-row>
      <el-row :gutter="24" v-show="isAdmin">
        <el-col :span="6" :offset="0">
          <Card
            title="/guarantee-manager/repair"
            num="报修管理"
            tip="及时处理用户的报修"
            type="violet"
            icon="el-icon-attract"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/guarantee-manager/complaint"
            num="投诉管理"
            tip="查看用户反映的问题/建议"
            type="violet"
            icon="el-icon-message"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card title="/user-manager/household" num="用户管理" tip="城市内用户账号的管理" type="blue" icon="el-icon-user" />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card title="/charge-manager/type" num="缴费管理" tip="城市内用户的费用管理" type="blue" icon="el-icon-coin" />
        </el-col>
      </el-row>
<!--      <el-row :gutter="24" v-show="isAdmin">-->
<!--        <el-col :span="6" :offset="0">-->
<!--          <Card-->
<!--            title="/system-manager/automatic-task"-->
<!--            num="自动任务"-->
<!--            tip="系统自动执行的任务管理"-->
<!--            type="aaa"-->
<!--            icon="el-icon-date"-->
<!--          />-->
<!--        </el-col>-->
<!--      </el-row>-->
      <el-row :gutter="24" v-show="!isAdmin">
        <el-col :span="6" :offset="0">
          <Card title="/user/base/info" num="个人信息" tip="修改自己的信息" type="blue" icon="el-icon-user" />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/user/base/reset_pwd"
            num="密码修改"
            tip="修改自己的密码"
            type="orange"
            icon="el-icon-lock"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/user/pay_record"
            num="生活缴费"
            tip="缴纳本月费用"
            type="pink"
            icon="el-icon-collection-tag
"
          />
        </el-col>
        <el-col :span="6" :offset="0">
          <Card
            title="/user/repair/add"
            num="申请报修"
            tip="设施损坏在此报修"
            type="aaa"
            icon="el-icon-tickets"
          />
        </el-col>
      </el-row>
      <el-row :gutter="24" v-show="!isAdmin">
        <el-col :span="6" :offset="0">
          <Card
            title="/user/complaint/add"
            num="发起投诉"
            tip="对服务进行投诉"
            type="violet"
            icon="el-icon-phone-outline"
          />
        </el-col>
      </el-row>
    </page-main>
  </div>
</template>

<script>
import card from '@/views/component_extend_example/card.vue'
export default {
  data () {
    return {
      isAdmin: false
    }
  },
  components: {
    'Card': card,
  },
  created () {
    let isAdmin = localStorage.getItem('isAdmin')
    this.isAdmin = isAdmin == 'true' ? true : false

  },
  methods: {
    open (url) {
      window.open(url, 'top')
    },
    onIconClick (val) {
      this.$message({
        message: `你点击了：${val}`,
        type: 'info'
      })
    },

  }
}
</script>

<style lang="scss" scoped>
.el-row {
    margin: 10px;
}
</style>
