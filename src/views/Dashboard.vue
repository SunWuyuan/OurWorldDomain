<style scoped>
.button-group {
  display: flex;
  gap: 15px;
  /* 调整间距大小 */
}
</style>
<template>
  <Toast /> 
  <div class="grid">
    <div class="col-12 xl:col-6">
      <div class="card">
        <div class="flex align-items-center justify-content-between mb-4">
          <h4>温馨提示</h4>
        </div>
        <span class="block text-600 font-medium mb-3">🔔使用提示</span>
        <h5 class="text-600">
          OurWorld Domain 欢迎使用！<br />
          访问 <a href="https://ourworld.wuyuan.dev/" target="_blank">OurWorld</a> 主站 <br />
        </h5>
        <br />
        <span class="block text-600 font-medium mb-3">🏆常用功能</span>
        <h6 class="button-group">
          <Button label="📅签到" @click="signIn" />
         <!-- <Button
            onclick="window.open('http://qm.qq.com/cgi-bin/qm/qr?_wv=1027&k=73T48TWm3nzVt5jSF6SyDVY2AoyZfMSu&authKey=As1WSDrOpm3nmJNkH6q1OQ3r%2FkyOD24hR7OBXDs0MkfQD5be1hTQo2HU8LRUNn57&noverify=0&group_code=230832864')">📢加入Q群</Button>
          <Button onclick="window.open('https://langsteam.feishu.cn/share/base/form/shrcn708g5ZIScs87gvWo0ms8yc')">参与新功能调查</Button>-->
          <br>
        </h6>
      </div>
    </div>
  </div>
</template>
<script setup>
import axios from '@/axios/axios'
import { useToast } from "primevue/usetoast"

const toast = useToast()

const signIn = () => {
  axios.get('/user/sign_in')
    .then(function (response) {
      if (response.data.code === 200) {
        toast.add({ severity: 'success', summary: '签到成功', detail: '您已签到成功', life: 3000 })
      } else {
        console.log(response.data)
        toast.add({ severity: 'error', summary: '签到失败', detail: '明天再来吧~', life: 3000 })
      }
    }).catch(function (error) {
      console.log(error)
    })
}
</script>