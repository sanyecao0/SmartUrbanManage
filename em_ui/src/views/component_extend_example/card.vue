<template>
  <div
    class="el-card mini-card is-hover-shadow"
    style="background: linear-gradient(76deg, rgb(132, 60, 246), rgb(117, 155, 255));"
  >
    <div :class="type">
      <!-- <div class="el-card__header">
        <div>{{title}}</div>
      </div>-->
      <div class="el-card__body">
        <el-button class="num" type="text" @click="openRouter()">{{num}}</el-button>
        <div class="tip">{{tip}}</div>
        <i :class="icon"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title', 'num', 'tip', 'type', 'icon'],
  data () {
    return {

    }
  },
  methods: {
    openRouter () {
      this.$router.push(this.title)
    }
  },
}
</script>

<style lang="scss" scoped>
.violet {
    background: linear-gradient(76deg, rgb(45, 34, 65), rgb(117, 155, 255));
}
.aaa {
    background: linear-gradient(76deg, rgb(202, 21, 30), rgb(233, 163, 71));
}
.pink {
    background: linear-gradient(50deg, rgb(251, 170, 162), rgb(252, 82, 134));
}
.green {
    background: linear-gradient(50deg, rgb(0, 0, 0), rgb(0, 245, 255));
}
.blue {
    background: linear-gradient(50deg, rgb(91, 209, 225), rgb(58, 50, 50));
}
i {
    font-size: 120px;
    position: absolute;
    right: -30px;
    top: -10px;
    -webkit-transform: rotate(15deg);
    transform: rotate(15deg);
}
.mini-card {
    width: 255px;
    position: relative;
    color: #fff;
}
.mini-card .num {
    color: #fff;
    font-weight: bold;
    font-size: 36px;
}
.mini-card .tip {
    margin-top: 10px;
    font-size: 17px;
    color: #eee;
}
.el-card__header {
    border-bottom: 0 solid #ebeef5;
}
</style>
