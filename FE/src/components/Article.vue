<template>
  <div>
    <div>
      <el-form ref="form" :model="article_form" label-width="100px">
        <el-form-item label="文件拖拽至此:">
          <el-input type="text" v-model="article_form.title" style="width: 100%;padding-left: 0px" clearable></el-input>
        </el-form-item>
        <el-form-item label="文件内容描述:">
          <el-input  type="textarea" :rows="10" placeholder="请输入内容" v-model="article_form.content"
          ></el-input>
          <el-upload
            class="upload-demo"
            action="https://jsonplaceholder.typicode.com/posts/"
            :on-preview="handlePreview"
            :on-remove="handleRemove"
            :before-remove="beforeRemove"
            multiple
            :limit="1"
            drag
            accept=".doc,.docx"
            :on-exceed="handleExceed"
            :file-list="fileList">
            <el-tooltip class="item" effect="dark" content="拖动文件到框中即可上传" placement="top">
            <el-button size="small" type="primary">点击上传</el-button>
            </el-tooltip>
            <div slot="tip" class="el-upload__tip">只能上传doc/docx文件</div>
          </el-upload>
        </el-form-item>
        <el-form-item label="相似度阈值:">
          <el-input type="text" v-model="article_form.thresold" style="width: 100px;padding-left: 0px" clearable></el-input>
        </el-form-item>
        <el-form-item label="查重方法选择:">
          <el-radio-group v-model="article_form.method">
            <el-radio label="SimHashWith01"></el-radio>
            <el-radio label="SimHashWithTFIDF"></el-radio>
            <el-radio label="MinHash"></el-radio>
          </el-radio-group>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">提交</el-button>
        </el-form-item>
      </el-form>
    </div>

    <div style="padding-top: 200px">
      <result></result>
    </div>
  </div>
</template>

<script>
  import Result from './Result'
export default {
  components:{
    'result': Result
  },
  data(){
    return{
      article_form:{
        title:'',
        content:'',
        thresold:'',
        method:''
      },
      fileList: []
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!');
      scroll(0,1000)
    },
    handleRemove(file, fileList) {
      console.log(file, fileList);
    },
    handlePreview(file) {
      console.log(file);
    },
    handleExceed(files, fileList) {
      this.$message.warning(`当前限制选择 3 个文件，本次选择了 ${files.length} 个文件，共选择了 ${files.length + fileList.length} 个文件`);
    },
    beforeRemove(file, fileList) {
      return this.$confirm(`确定移除 ${ file.name }？`);
    }
  }
}
</script>

<style scoped>
</style>
