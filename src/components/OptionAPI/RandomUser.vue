<script>
export default {
  data() {
    return {
      userImg: "",
      userName: "",
    };
  },
  methods: {
    async fetchUser() {
      const response = await fetch("https://randomuser.me/api/");
      const data = await response.json();

      this.userImg = data.results[0].picture.large;
      this.userName = data.results[0].name.first;
    },
  },
};
</script>

<template>
  <div  class="user-card">
    <div class="user-img">
      <img v-if="userImg" :src="userImg" />
    </div>
    <h3 class="user-name">{{ userName }}</h3>
    <button @click="fetchUser" class="user-btn">get new user</button>
  </div>
</template>
<style scoped>
.user-card{
  box-sizing: content-box ;
  height: 200px;
  width: 150px;

  padding: 24px 12px 12px 12px;
  
  border-radius: 12px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;

  gap: 21px;

  background-color: #eee;


}
.user-img {
  width: 80px;
  height: 80px;

  overflow: hidden;
  border-radius: 100%;

  background-color: grey;
}
.user-img img {
  width: 100%;
  height: 100%;
}
.user-btn{
  width: 100%;
  
  padding: 9px;
  
  border-radius: 6px;
  border: none;

  cursor: pointer;
  background-color: aquamarine;
}
</style>
