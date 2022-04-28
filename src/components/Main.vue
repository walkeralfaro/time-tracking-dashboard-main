<template>
    <div class="card">

      <div class="cardExt">
        <div class="fle">
          <div class="card__image">
            <img src="@/assets/images/image-jeremy.png" alt="person_image">
          </div>
          <div class="report">
            <p>Report for</p>
          </div>
          <h1 class="main__name">
            Jeremy Robson
          </h1>
        </div>
      </div>

      <div class="cardInt">
        <div class="flex">

          <div class="period__selection">
            <select v-model="periodSelected" multiple>
              <option>Daily</option>
              <option>Weekly</option>
              <option>Monthly</option>
            </select>
          </div>
        </div>

      </div>
      
  </div>
</template>

<script>
export default {
  data() {
    return {
      periodSelected: ['Daily']
    }
  },

  emits: ['periodSelected'],

  created() {
    this.$emit('periodSelected',  this.periodSelected[0])
  },

  beforeUpdate() {
    this.$emit('periodSelected',  this.periodSelected[0])
  }

}
</script>

<style>

</style>