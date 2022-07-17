<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div @click="changeBtn">{{ pageChange }}</div>
    <float-btn />
  </div>
</template>

<script>
import FloatBtn from './floatBtn.vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  components: {
    FloatBtn,
  },
  data() {
    return {
      pageChange: '放大页面',
      scal: '1',
    }
  },
  methods: {
    changeBtn() {
      let getBody = document.getElementById('app').style
      if (this.pageChange == '放大页面') {
        // Firefox
        if (navigator.userAgent.indexOf('Firefox') > 0) {
          this.scal = (parseFloat(this.scal) + 0.5).toFixed(2)
          getBody.transform = `scale(${this.scal})`
          getBody.transformOrigin = 'center top'
        } else {
          getBody.setProperty('zoom', '1.5')
        }
        this.pageChange = '正常页面'
      } else {
        // Firefox
        if (navigator.userAgent.indexOf('Firefox') > 0) {
          this.scal = (parseFloat(this.scal) - 0.5).toFixed(2)
          getBody.transform = `scale(${this.scal})`
          getBody.transformOrigin = '0.0'
        } else {
          getBody.removeProperty('zoom')
        }
        this.pageChange = '放大页面'
      }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
