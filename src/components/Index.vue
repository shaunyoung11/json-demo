<template>
  <div class="index">
    <h2 class="page-title">{{ pageTitle }}</h2>
    <v-data-table
      class="index-table"
      :headers="headers"
      :items="usrInfo"
      :items-per-page="5"
    ></v-data-table>
    <v-btn outlined @click="handleGetUserInfo">刷新数据</v-btn>
  </div>
</template>

<script>
export default {
  data() {
    return {
      usrInfo: [],
      pageTitle: '暂时还未获取到页面标题',
      headers: [
        {
          text: 'Name',
          value: 'name'
        },
        {
          text: 'Age',
          value: 'age'
        },
        {
          text: 'Phone',
          value: 'phone'
        }
      ]
    }
  },
  created() {
    this.handleGetUserInfo()
  },
  methods: {
    // 获取用户信息方法
    handleGetUserInfo() {
      this.$https.get('/shaunyoung/usr').then(res => {
        console.log(res)
        this.$data.usrInfo = res.data.info
        this.$data.pageTitle = res.data.title
      })
    }
  }
}
</script>

<style scoped>
.index {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

.index-table {
  width: 70%;
}
</style>
