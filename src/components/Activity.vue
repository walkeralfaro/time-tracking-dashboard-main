<template>
  <div class="card">
    <div class="cardExt" :class="title">
        <div class="cardImg">
            <img :src="imgSrc" alt="activity" />
        </div>

      <div class="cardInt">
        <div class="flexInt">
          <div class="title">
            <h2 class="titleFrame">{{ title }}</h2>
            <div>
              <img
                class="ellipsis"
                src="@/assets/images/icon-ellipsis.svg"
                alt="ellipsis"
              />
            </div>
          </div>
          <div class="hours">
            <p class="currentHours">{{ current }}hrs</p>
            <p class="lastHours">Last Week - {{ previous }}hrs</p>
          </div>
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
      required: true,
    },
    current: {
      type: Number,
      required: true,
    },
    previous: {
      type: Number,
      required: true,
    },
  },

  computed: {
    imgSrc() {
      const imgTitle = this.title.toLowerCase().replace(" ", "-");
      return `assets/images/icon-${imgTitle}.svg`;
    },
  },
};
</script>

<style scoped>
.cardInt {
    background-color: var(--DarkBlue);
    height: 15rem;
}

.cardExt {
    border-radius: 1rem;
    position: relative;
    z-index: -12;
    height: 20rem;


}

.cardImg {
    display: flex;
    flex-direction: row-reverse;



}

.cardImg img {

    position: absolute;
    top: -1rem;
    z-index: -1;




}

.Exercise .cardImg img{

    position: absolute;
    top: 0;
    z-index: -1;

}


</style>