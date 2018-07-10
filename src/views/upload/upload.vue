<template>
  <section class="form-section">
    <el-upload
      class="upload-demo"
      ref="upload"
      action="http://127.0.0.1:8080/upload/resume"
      multiple
      :limit="10"
      :on-preview="handlePreview"
      :on-remove="handleRemove"
      :file-list="fileList"
      :auto-upload="false">
      <el-button slot="trigger" size="small" type="primary">选取文件</el-button>
      <el-button style="margin-left: 10px;" size="small" type="success" @click="submitUpload">上传到服务器</el-button>
      <div slot="tip" class="el-upload__tip">仅支持格word、PDF、HTML格式，单次最多上传10份</div>
    </el-upload>
  </section>
</template>
<script>
export default {
    data() {
      return {
        fileList: []
      };
    },
    methods: {
      submitUpload() {
        this.$refs.upload.submit();
      },
      handleRemove(file, fileList) {
        console.log(file, fileList);
      },
      handlePreview(file) {
        console.log(file);
      }
    }
  }
</script>
