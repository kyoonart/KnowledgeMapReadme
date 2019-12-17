<template>
  <div>
    <el-form ref="form" :model="paragraph_form" label-width="100px" >
      <el-form-item label="内容描述:">
        <el-input  type="textarea" :rows="10" placeholder="请输入内容" v-model="paragraph_form.content" style="width: 100% "
        ></el-input>
      </el-form-item>
      <el-form-item label="相似度阈值:">
        <el-input type="text" v-model="paragraph_form.thresold" style="width: 100px;padding-left: 0px" clearable></el-input>
      </el-form-item>
      <el-form-item label="查重方法选择:">
        <el-radio-group v-model="paragraph_form.method">
          <el-radio label="SimHashWith01"></el-radio>
          <el-radio label="SimHashWithTFIDF"></el-radio>
          <el-radio label="MinHash"></el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">提交</el-button>
      </el-form-item>
    </el-form>
    <div  id="/Paragraph/Result" style="padding-top: 400px">
      <result></result>
    </div>
  </div>
</template>

<script type="text/javascript">
  import Result from "./Result";
  export default {
    components: {
      'result':Result
    },
    data(){
      return{
        paragraph_form:{
          content:'',
          thresold:'',
          method:''
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
        scroll(0,900)
        //location.hash='/Paragraph/Result'
        //this.$router.push({path:'/Paragraph/Result'});
      }
    }
  }
</script>

<style>

</style>
