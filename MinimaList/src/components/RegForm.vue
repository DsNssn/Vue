<template>
  <form class="form-wrapper">
    <div class="info">快速注册</div>
    <div class="form-input">
      <label>用户名</label>
      <input type="text" v-model="name">
    </div>
    <div class="form-input">
      <label>密码</label>
      <input type="password" v-model="password">
    </div>
    <div class="form-input">
      <label>确认密码</label>
      <input type="password" v-model="passwordRepeart">
    </div>
    <div class="btns">
      <button type="button" @click="reg()">注册</button>
      <button type="button" @click="()=>{this.$router.back()}">取消</button>
    </div>
  </form>
</template>

<script>
export default {
  name: 'RegForm',
  data () {
    return {
      name: '',
      password: '',
      passwordRepeart: ''
    }
  },
  methods: {
    reg () {
      if (this.password === this.passwordRepeart && this.name !== '') {
        localStorage.setItem('name', this.name)
        localStorage.setItem('password', this.password)
        this.$router.push({ name: 'login' })
      } else {
        alert('请检查密码是否输入一致')
      }
    }
  }
}
</script>

<style scoped>
.info{
  padding: 30px;
  font-size: 18px;
  font-weight: bold;
  color: #757575;
}
.btns{
  padding-top: 30px;
}
</style>
