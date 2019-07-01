<template>
  <div>
    <h1>User View</h1>
    <VUserSearchForm/>
    <VUserProfile :user="user"/>
  </div>
</template>

<script>
import VUserSearchForm from "@/components/VUserSearchForm";
import VUserProfile from "@/components/VUserProfile";

export default {
  name: "UserViews",
  components: { VUserSearchForm, VUserProfile },
  data() {
    return {
      user: { name: '' }
    }
  }
};
</script>
