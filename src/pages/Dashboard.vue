<template>
<!-- <div class="container"> -->
  <div class="flex">
    <div class="grid">
      <Main @periodSelected="(period) => periodSelect = period.toLowerCase()"/>

      <div v-if="periodSelect==='daily'" class="grid__activities">
        <Activity
          v-for="activity in activities" :key="activity"
          :title="activity.title"
          :current="activity.timeframes.daily.current"
          :previous="activity.timeframes.daily.previous"
        />
      </div>

      <div v-if="periodSelect==='weekly'" class="grid__activities">
        <Activity
          v-for="activity in activities" :key="activity"
          :title="activity.title"
          :current="activity.timeframes.weekly.current"
          :previous="activity.timeframes.weekly.previous"
        />
      </div>

      <div v-if="periodSelect==='monthly'" class="grid__activities">
        <Activity
          v-for="activity in activities" :key="activity"
          :title="activity.title"
          :current="activity.timeframes.monthly.current"
          :previous="activity.timeframes.monthly.previous"
        />
      </div>
    </div>
  </div>
<!-- </div> -->

</template>

<script>
import Main from '@/components/Main'
import Activity from '@/components/Activity'
import activitiesData from '@/assets/data/data'

export default {
  components: { Activity, Main },
  data() {
    return {
      periodSelect: '',
      activities: activitiesData,
    }
  }
}
</script>

<style scoped>

.flex {
  display: flex;
  justify-content: center;
  align-items: center;
  width:100%;
	height:100vh;
}






</style>