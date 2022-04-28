<template>
  <div class="card">

      <div class="cardExt">
          <img :src=imgSrc alt="activity">
      </div>

      <div class="cardInt">
        <div class="flex">
            <div class="title">
                <h2 class="titleFrame">{{ title }}</h2>
                <div>
                    <img class="ellipsis" src="@/assets/images/icon-ellipsis.svg" alt="ellipsis">
                </div>
            </div>
            <div class="hours">
                <p class="currentHours">{{ current }}hrs</p>
                <p class="lastHours"> Last Week - {{ previous }}hrs</p>
            </div>
        </div>
      </div>
      
  </div>
</template>

<script>


export default {

    props: {
        title: {
            type: String,
            required: true
        },
        current: {
            type: Number,
            required: true
        },
        previous: {
            type: Number,
            required: true
        }
    },

    computed: {
        imgSrc() {
            const imgTitle = this.title.toLowerCase().replace(' ', '-')
            return `assets/images/icon-${imgTitle}.svg`
        }
    }

}
</script>

<style scoped>



</style>