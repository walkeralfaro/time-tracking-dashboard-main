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
        <button
         @click="$emit('periodSelected', 'daily')" 
         :class="periodSelect === 'daily' ? 'press' : null">
        Daily
        </button>
        <button
         @click="$emit('periodSelected', 'weekly')" 
         :class="periodSelect === 'weekly' ? 'press' : null">
         Weekly
        </button>
        <button
         @click="$emit('periodSelected', 'monthly')" 
         :class="periodSelect === 'monthly' ? 'press' : null">
         Monthly
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: "Principal",
props: ["periodSelect"],
};
</script>

<style scoped>
.main__card {
  width: 100%;
  height: 100%;
}

.cardExt {
  background-color: var(--DarkBlue);
  border-radius: 1.5rem;
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

.card__image img {
  width: 9rem;
  border: 3px solid white;
  border-radius: 50%;
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

.cardInt {
  height: 30%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;

}

.cardInt button {
  border: none;
  background: none;
  color: var(--PaleBlue);
  font-size: 1.8rem;
  margin: 1rem;
  margin-left: 3rem;
  cursor: pointer;
}

.cardInt button.press {
  color: white;
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
    flex-direction: row;
    align-items: center;
    height: 5rem;
  }

  .cardInt button {
    margin: 2rem;
}

}
</style>