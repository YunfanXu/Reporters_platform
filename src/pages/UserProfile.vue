<template>
  <div class="row">
    <div class="col-xl-4 col-lg-5 col-md-6">
      <user-card> </user-card>
    </div>
    <div class="col-xl-8 col-lg-7 col-md-6">
      <edit-profile-form> </edit-profile-form>
    </div>
    <div class="col-xl-8 col-lg-7 col-md-6">
      <manage-certificates-card> </manage-certificates-card>
    </div>
    <div class="col-xl-4 col-lg-5 col-md-6">
      <members-card> </members-card>
    </div>
  </div>
</template>
<script>
import EditProfileForm from "./UserProfile/EditProfileForm.vue";
import UserCard from "./UserProfile/UserCard.vue";
import MembersCard from "./UserProfile/MembersCard.vue";
import ManageCertificatesCard from "./UserProfile/ManageCertificatesCard.vue";
export default {
  components: {
    EditProfileForm,
    UserCard,
    MembersCard,
    ManageCertificatesCard,
  },
};
</script>
<style>
</style>
