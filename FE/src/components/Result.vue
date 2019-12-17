<template>
<div>
  <div>
    <el-header> <h2>检测报告</h2></el-header>
    <el-table
      :data="BasicData"
      stripe
      border
      fit
      >
      <el-table-column prop="title" label="">
      </el-table-column>
      <el-table-column prop="message" label="基本信息" width="1200px" >
      </el-table-column>
    </el-table>
    <el-header> <h2>相似片段位置图</h2></el-header>
      <div><img src=""/></div>
      <div class="nui-scroll"></div>
    <el-header> <h2>报告详情</h2></el-header>
  </div>
  <div v-show="chek">
    <el-tabs v-model="activeName" type="card" @tab-click="handleClick">
      <el-tab-pane label="标题重复" name="TitleReport">
        <title-report></title-report>
      </el-tab-pane>
      <el-tab-pane label="正文重复" name="ArticleReport">
        <article-report></article-report>
      </el-tab-pane>
    </el-tabs>
  </div>
  <div v-show="chek1">
    <article-report></article-report>
  </div>
  <el-pagination
    background
    layout="prev, pager, next"
    :total="80" align="center">
  </el-pagination>
  <div align="center" style="margin-top: 30px">
    <el-button type="primary" @click="onSubmit">回到顶部</el-button>
  </div>
</div>
</template>

<script>
  import TitleReport from './TitleReport'
  import ArticleReport from './ArticleReport'
export default {

    components:{
      'title-report':TitleReport,
      'article-report':ArticleReport
    },
  data() {
    return {
      BasicData: [{
        title:'报告编号:',
        message:''
      },{
        title:'检测范围:',
        message:''
      },{
        title:'总相似率:',
        message:'',
      }
      ],
      scrolldelay:'',
      activeName: 'TitleReport'
    }
  },
  methods:{
    onSubmit(){
      scroll(0,0);
      //this.$router.go(-1);
    },
    handleClick(tab, event) {
      //console.log(tab, event);
    }
  },
  computed:{
      chek(){
        var path = this.$route.path;
        if(path == '/Article'){
          return true;
        }
        else return false
      },
      chek1(){
        var path = this.$route.path;
        if(path == '/Paragraph'){
          return true;
        }
        else return false
      }
  }
}
</script>

<style>
.content{
  width: 100%;
  height: 400px;
  border: #dcdfe6 solid 1px;
  border-radius: 5px;
  overflow: scroll;
  overflow-x: hidden;
  font-size: 18px;
}
.nui-scroll{
  width: 100%;
  height: 400px;
  border: #dcdfe6 solid 1px;
  border-radius: 5px;
  overflow: scroll;
  overflow-x: hidden;
  font-size: 18px;
}
.nui-scroll::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}
/*正常情况下滑块的样式*/
.nui-scroll::-webkit-scrollbar-thumb {
  background-color: rgba(0,0,0,.05);
  border-radius: 10px;
  -webkit-box-shadow: inset 1px 1px 0 rgba(0,0,0,.1);
}
/*鼠标悬浮在该类指向的控件上时滑块的样式*/
.nui-scroll:hover::-webkit-scrollbar-thumb {
  background-color: rgba(0,0,0,.2);
  border-radius: 10px;
  -webkit-box-shadow: inset 1px 1px 0 rgba(0,0,0,.1);
}
/*鼠标悬浮在滑块上时滑块的样式*/
.nui-scroll::-webkit-scrollbar-thumb:hover {
  background-color: rgba(0,0,0,.4);
  -webkit-box-shadow: inset 1px 1px 0 rgba(0,0,0,.1);
}
/*正常时候的主干部分*/
.nui-scroll::-webkit-scrollbar-track {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0);
  background-color: white;
}
/*鼠标悬浮在滚动条上的主干部分*/
.nui-scroll::-webkit-scrollbar-track:hover {
  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.4);
  background-color: rgba(0,0,0,.01);
}
</style>
