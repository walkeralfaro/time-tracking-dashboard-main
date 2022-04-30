<template>
  <!-- <div class="container"> -->
  <div class="flex">
    <div class="grid">
      <Main
        @periodSelected="(period) => (periodSelect = period.toLowerCase())"
      />

      <div class="grid__activities">
        <activity
          v-for="activity in activities"
          :key="activity"
          :title="activity.title"
        >
          <div v-if="periodSelect === 'daily'" class="time">
            <p class="hoursCurrent">
              {{ activity.timeframes.daily.current }}hrs
            </p>
            <p class="hoursPrevious">
              Last Day - {{ activity.timeframes.daily.previous }}hrs
            </p>
          </div>

          <div v-else-if="periodSelect === 'weekly'" class="time">
            <p class="hoursCurrent">
              {{ activity.timeframes.weekly.current }}hrs
            </p>
            <p class="hoursPrevious">
              Last Week - {{ activity.timeframes.weekly.previous }}hrs
            </p>
          </div>

          <div v-else-if="periodSelect === 'monthly'" class="time">
            <p class="hoursCurrent">
              {{ activity.timeframes.monthly.current }}hrs
            </p>
            <p class="hoursPrevious">
              Last Month - {{ activity.timeframes.monthly.previous }}hrs
            </p>
          </div>
        </activity>
      </div>
    </div>
  </div>
  <!-- </div> -->
</template>

<script>
import Main from "@/components/Main";
import Activity from "@/components/Activity";
import activitiesData from "@/assets/data/data";

export default {
  name: "Padre",
  components: { Activity, Main },
  data() {
    return {
      periodSelect: "",
      activities: activitiesData,
    };
  },
};
</script>

<style scoped>
.flex {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  min-height: 100vh;
}

.hoursCurrent {
  font-size: 6rem;
  margin: 0;
  padding: 0;
  font-weight: 300;
  padding-bottom: 1rem;
}

.hoursPrevious {
  font-size: 1.6rem;
  margin: 0;
  padding: 0;
  font-weight: 400;
  color: var(--PaleBlue);
}

@media (max-width: 1280px) {
  p.hoursCurrent {
    font-size: 4.5rem;
  }
  p.hoursPrevious {
    font-size: 1.3rem;
  }
}

@media (max-width: 1024px) {
  .time {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  p.hoursCurrent {
    font-size: 4rem;
  }
  p.hoursPrevious {
    font-size: 1.2rem;
  }
}
</style>