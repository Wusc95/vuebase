<template>
  <div class="container">
    <v-picker-range ref="VPickerRange" disabled-rule="after" default-date-type="yesterday">
    </v-picker-range>
    <el-button type="primary" @click="getNowTime">获取当前时间</el-button>
    <div>{{time}}</div>
    <div>开始时间：{{startDate}}</div>
    <div>结束时间：{{endDate}}</div>
    <v-picker-range ref="VPickerRange2" type="datetimerange" formatter="yyyy-MM-dd HH:mm:ss" default-date-type="today">
    </v-picker-range>
    <el-button type="primary" @click="getNowTime2">获取当前时间</el-button>
    <div>{{time2}}</div>
    <div>开始时间：{{startDate2}}</div>
    <div>结束时间：{{endDate2}}</div>
    <v-picker-range ref="VPickerRange3" :is-show-quick="false" algin="right">
    </v-picker-range>
  </div>
</template>

<script>
  import VPickerRange from '@/components/VPickerRange'

  export default {
    name: 'PluginTime',
    components: {VPickerRange},
    props: {},
    data() {
      return {
        time: '',
        startDate: '',
        endDate: '',
        time2: '',
        startDate2: '',
        endDate2: ''
      }
    },
    created() {

    },
    mounted() {

    },
    methods: {
      getNowTime() {
        this.time = this.$refs.VPickerRange.time;
        let timeObj = this.$refs.VPickerRange.getTimeObj('startDate', 'endDate');
        this.startDate = timeObj.startDate;
        this.endDate = timeObj.endDate;
        console.log(this.startDate, this.endDate)
      },
      getNowTime2() {
        this.time2 = this.$refs.VPickerRange2.time;
        // getTimeObj传的是什么名字，返回来的timeObj就是什么key
        let timeObj = this.$refs.VPickerRange2.getTimeObj('startTime', 'endTime');
        this.startDate2 = timeObj.startTime;
        this.endDate2 = timeObj.endTime;
      }
    },
    computed: {},
    watch: {}
  }
</script>

<style lang="scss">

</style>
