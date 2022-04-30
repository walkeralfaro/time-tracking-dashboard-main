<template>
  <div class="main__card">
    <div class="cardExt">
      <div class="flexExt">
        <div class="card__image">
          <img src="@/assets/images/image-jeremy.png" alt="person_image" />
        </div>
        <div class="report">
          <p>Report for</p>
          <h1 class="main__name">Jeremy Robson</h1>
        </div>
      </div>
      <div class="cardInt">
        <select v-model="periodSelected" multiple class="period__options">
          <option>Daily</option>
          <option>Weekly</option>
          <option>Monthly</option>
        </select>
        <div class="aux"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      periodSelected: ["Daily"],
    };
  },

  emits: ["periodSelected"],

  created() {
    this.$emit("periodSelected", this.periodSelected[0]);
  },

  beforeUpdate() {
    this.$emit("periodSelected", this.periodSelected[0]);
  },
};
</script>

<style scoped>
.main__card {
  width: 100%;
  height: 100%;
}

.flexExt {
  padding: 4rem;
  display: flex;
  flex-direction: column;
  background-color: var(--Blue);
  border-radius: 1.5rem;
  height: 70%;
}

.main__name {
  font-weight: 300;
  font-size: 4.4rem;
  margin: 0;
  padding: 0;
}

.report p {
  color: var(--PaleBlue);
  margin: 5rem 0 0 0;
  font-size: 1.6rem;
}

.cardExt {
  background-color: var(--DarkBlue);
  border-radius: 1.5rem;
  width: 100%;
  height: 100%;
}

.cardInt {
  height: 30%;
  display: flex;
  align-items: center;
  position: relative;
}

.period__options {
  font-size: 1.8rem;
  font-weight: 400;
  height: 72%;
  padding: 0 4rem 0 4rem;
}

.period__options option {
  padding-bottom: 1.5rem;
}

.card__image img {
  width: 9rem;
  border: 3px solid white;
  border-radius: 50%;
}

select[multiple]:focus option:checked {
  background: linear-gradient(
    0deg,
    hsl(235, 46%, 20%) 100%,
    hsl(235, 46%, 20%) 100%
  );
}

select[multiple] option:checked {
  -webkit-text-fill-color: white;
  color: white;
}

select[multiple] option {
  background: linear-gradient(
    0deg,
    hsl(235, 46%, 20%) 100%,
    hsl(235, 46%, 20%) 100%
  );
  -webkit-text-fill-color: var(--PaleBlue);
  -moz-text-fill-color: var(--PaleBlue);
  cursor: pointer;
}

select.period__options {
  background: none;
  border: none;
  outline: none;
}

div.aux {
  position: absolute;
  left: 15rem;
  height: 15rem;
  width: 5rem;
  background: var(--DarkBlue);
  z-index: 10;
}

@media (max-width: 1024px) {
  .flexExt {
    padding: 2.5rem;
    display: flex;
    flex-flow: row;
    height: 11rem;
  }

  .report {
    margin: 0 auto;
  }

  .report p {
    margin-top: 0px;
  }

  .main__name {
    font-size: 2.45rem;
  }

  .card__image img {
    width: 6rem;
    border: 3px solid white;
    border-radius: 50%;
  }

  .cardInt {
    height: 17rem;
  }

  select.period__options {
    background: none;
    border: none;
    outline: none;
  }
}
</style>