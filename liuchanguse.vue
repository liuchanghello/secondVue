<template>
<div id='packed'>
    <h4>如果不是你我不会相信</h4>
    <span>一定是你啊 招招找</span>
    <button @click='msgClick'>点我啊</button>
  <h3>招逸枫</h3>

  <el-button type="primary" plain disabled>主要按钮</el-button>
  <br>
  <br>
  <br>
  <br>
  <el-upload
  class="upload-demo"
  action="https://jsonplaceholder.typicode.com/posts/"
  :on-preview="handlePreview"
  :on-remove="handleRemove"
  :before-remove="beforeRemove"
  multiple
  :limit="3"
  :on-exceed="handleExceed"
  :file-list="fileList">
  <el-button size="small" type="primary">点击上传</el-button>
  <div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>

 
</el-upload>

 <el-switch
  v-model="value"
  active-color="#13ce66"
  inactive-color="#ff4949">
</el-switch>
  </div>
</template>

<script>
export default {
 data() {
      return {
        fileList: [],
        value:true
      };
    },
    methods: {
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
      },
      msgClick(){
          alert('说点咱就点')
      }
    }
}
</script>

<style>

</style>