<template>
  <div class="people-section">
    <img :src="profilePicture"/>
    <div class="people-section__info">
      <div class="people-section__info__name">{{ userName }}</div>
      <div class="people-section__info__role">{{ role }}</div>
<!--      <div class="people-section__info__partnership">{{ partnership }}</div>-->
    </div>
  </div>
</template>

<script>
export default {
  name: "PeopleSection",
  props: {
    profilePicture: {
      type: String,
      default: "#"
    },
    userName: {
      type: String,
      default: '',
    },
    partnership: {
      type: String,
      default: '',
    },
    role: {
      type: String,
      default: '',
    }
  }
}
</script>

<style lang="scss" scoped>
.people-section {
  display: flex;
  img {
    min-width: 75px;
    min-height: 75px;
    max-width: 75px;
    max-height: 75px;
    border-radius: 50%;
  }
  &__info {
    display: flex;
    flex-direction: column;
    margin-left: 30px;
    margin-bottom: 30px;
    &__name {
      font-size: 17px;
      font-weight: bold;
      color: black;
    }
    //&__role {
    //  color: gray;
    //  font-size: 14px;
    //}
  }
}
</style>
