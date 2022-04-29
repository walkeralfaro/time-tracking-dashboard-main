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
            <div class="ellipsis">
              <img
                class="ellipsis"
                src="@/assets/images/icon-ellipsis.svg"
                alt="ellipsis"
              />
            </div>
          </div>
          <!-- Draw the time -->
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Actividad",
  props: {
    title: {
      type: String,
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
.card {
  width: 100%;
  height: 25rem;
  min-width: 20rem;
  min-height: 20rem;
}

.cardExt {
  border-radius: 1.5rem;
  position: relative;
  height: 100%;
}

.cardImg {
  height: 100%;
  overflow: hidden;
  position: relative;
}

.cardImg img {
  position: absolute;
  top: -1rem;
  right: 15px;
}

.Exercise .cardImg img {
  top: 0;
}

.cardInt {
  background-color: var(--DarkBlue);
  height: 15rem;
  border-radius: 1.2rem;
  position: absolute;
  width: 100%;
  bottom: 0;
  height: 80%;
  cursor: pointer;
}

.cardInt:hover {
  background-color: var(--Aux);
}

.ellipsis:hover {
  filter: brightness(0) saturate(100%) invert(99%) sepia(8%) saturate(883%)
    hue-rotate(290deg) brightness(117%) contrast(100%);
}

.flexInt {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 3rem;
  height: 100%;
}

.title {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.titleFrame {
  margin: 0;
  font-weight: 400;
  font-size: 2rem;
}
</style>