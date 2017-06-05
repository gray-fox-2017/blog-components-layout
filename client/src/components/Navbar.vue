<template lang="html">
  <div>
    <el-menu theme="dark" class="el-menu-demo" mode="horizontal">
      <el-menu-item index="1">Blog Components Layout</el-menu-item>
    </el-menu>
    <el-row>
      <el-col :span="6">
        <el-menu default-active="2" class="el-menu-vertical-demo">
          <Sidebar v-for="(article, index) in articles" :key="article._id" v-bind:title="article" v-on:ijinaksesdataparent="kasihijin(index)"></Sidebar>
        </el-menu>
      </el-col>
      <el-col :span="18">
        <h2>Welcome</h2>
        <Content v-bind:detail="listdata"></Content>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import Sidebar from './Sidebar'
import Content from './Content'

export default {
  components: {
    Sidebar,
    Content
  },
  data() {
    return {
      articles: [],
      listdata: ''
    }
  },
  methods: {
    getAllArticle(){
      axios.get('http://localhost:3000/getallblog')
      .then(response => {
        console.log(response);
        this.articles = response.data
      })
    },
    kasihijin(index){
      this.listdata = this.articles[index]
      console.log('ini listdata');
      console.log(this.listdata);
    }
  },
  created(){
    this.getAllArticle()
  }
}
</script>

<style lang="css">
</style>
