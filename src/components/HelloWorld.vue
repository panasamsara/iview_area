<template>
  <div style="padding: 15px;">
    <Row>
      <Col span="4">
      <Cascader :data="data2" v-model="value2" @on-change="getArea"></Cascader>
      </Col>
      <Col span="4" style="text-align: center">
      <Button type="info" @click="query">查询</Button>
      <Button type="info" @click="reset">重置</Button>
      </Col>
    </Row>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        value2: ['11', '1101', '110102'],
        data2: this.AREA,
        args: ['北京', '市辖区', '西城区']
      }
    },
    created() {

    },
    methods: {
      query() {
        console.log(this.args)
      },
      reset() {
        this.value2 = []
        this.args = []
      },
      getArea(value, selectedData) {
        const areaName = selectedData.map(item => item.label)
        this.args = [...areaName]
      }
    }
  }

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
