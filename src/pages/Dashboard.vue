<template>
  <Main @periodSelected="(period) => periodSelect = period.toLowerCase()"/>

  <div v-if="periodSelect==='daily'" >
    <Activity
      v-for="activity in activities" :key="activity"
      :title="activity.title"
      :current="activity.timeframes.daily.current"
      :previous="activity.timeframes.daily.previous"
    />
  </div>

  <div v-if="periodSelect==='weekly'" >
    <Activity
      v-for="activity in activities" :key="activity"
      :title="activity.title"
      :current="activity.timeframes.weekly.current"
      :previous="activity.timeframes.weekly.previous"
    />
  </div>

  <div v-if="periodSelect==='monthly'" >
    <Activity
      v-for="activity in activities" :key="activity"
      :title="activity.title"
      :current="activity.timeframes.monthly.current"
      :previous="activity.timeframes.monthly.previous"
    />
  </div>

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

<style>

</style>