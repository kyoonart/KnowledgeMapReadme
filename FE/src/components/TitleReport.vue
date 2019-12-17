<template>
  <div style="padding-bottom: 20px">
      <div>
        <el-collapse v-model="activeNames" accordion>
        <el-collapse-item title="结果" name="1" >
          <table border="1px" style="width: 100%">
            <tr>
              <th style="width: 5%">序号</th>
              <td style="width: 45%">{id}</td>
              <th style="width: 5%">相似比</th>
              <el-tooltip class="item" effect="dark" :content=SimilarityDe placement="top">
                <td style="width: 45%">{Similarity degree}</td>
              </el-tooltip>
            </tr>
            <tr v-show="chek">
              <th >标题</th>
              <td colspan="3">{title}</td>
            </tr>
            <tr>
              <th >发表时间</th>
              <td colspan="3">date</td>
            </tr>
            <tr>
              <th>来源</th>
              <td colspan="3"><a href="https://www.baidu.com/">百度</a></td>
            </tr>
            <tr>
              <th>相似部分</th>
              <td class="contentco" colspan="3"><p>
                {文字高亮}
              </p></td>
            </tr>
          </table>
          </el-collapse-item>
        </el-collapse>
      </div>
  </div>
</template>

<script>
export default {
data(){
  return{
    activeNames:'1',
    SimilarityDe:'1',
  }
},
  computed:{
    chek(){
      var  path = this.$route.path;
      //console.log(path)
      if(path == '/Paragraph')
        return false;
      else return true
    }
  }
}
</script>

<style>
  .contentco{
    width: 80%;height: 200px;font-size: 18px
  }
  table {
    width: 200px;
    min-height: 25px;
    line-height: 25px;
    text-align: left;
    border-color: #dcdfe6;
    border-collapse: collapse;}
</style>
