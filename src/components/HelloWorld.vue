<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" v-model="code.name" /><br />
    <input type="text" v-model="code.surname" /><br />
    <input type="number" v-model="code.age" />
  
    <qrcode-vue :value="JSON.stringify(code)" :size="size" level="H"></qrcode-vue>
  </div>
</template>

<script>
import QrcodeVue from 'qrcode.vue';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      code: {},
      size: 250
    }
  },
  updated() {
    console.log(JSON.stringify(this.code));
  },
  components: {
    QrcodeVue
  }
}
</script>

<style scoped>

</style>
