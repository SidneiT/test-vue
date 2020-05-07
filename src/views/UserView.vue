<template>
  <div>
    <VUserSearchForm @submitted="searchUser"/>
    <VUserProfile :user="user"/>
  </div>
</template>

<script>
import { mapState } from "vuex";
import VUserSearchForm from "@/components/VUserSearchForm";
import VUserProfile from "@/components/VUserProfile";

export default {
  name: "UserView",
  components: {
    VUserSearchForm,
    VUserProfile
  },
  methods: {
    searchUser(username) {
      this.$store.dispatch("SEARCH_USER", { username });
    }
  },
  computed: {
    ...mapState({
      user: "user"
    })
  }
};
</script>
<style scoped>
.user-profile {
  border-top: solid 1px #ccc;
  padding-top: 20px;
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.user-profile__avatar {
  border-radius: 50%;
  width: 150px;
  height: 150px;
}
.user-profile__name {
  margin-top: 14px;
  font-size: 24px;
  font-family: "Bungee", cursive;
  text-transform: uppercase;
}
.user-profile__bio {
  margin-top: 14px;
  font-family: "Open Sans", sans-serif;
}
</style>