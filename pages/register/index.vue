<template>
  <div>
    <v-app-bar color="primary" flat dark>
      <v-toolbar-title>Register</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-o pb-0">
      <v-row>
        <v-col cols="12">
          <div class="mt-8 text-primary text-tiltle text-center">
            Step 1 of 2
          </div>
        </v-col>
        <v-col cols="12" class="text-center pb-0">
          <img src="~/assets/profile.png" alt="" width="155" />
        </v-col>
        <v-col cols="12" class="text-center pt-2 pb-0"> Display name </v-col>
        <v-col cols="12">
          <v-form>
            <v-text-field
              v-model="form.firstname"
              label="FirstName"
              dense
              required
            ></v-text-field>
            <v-text-field
              v-model="form.lastname"
              label="LastName"
              dense
              required
            ></v-text-field>
            <div class="gender-group d-flex mt-3">
              <p>Gender</p>
              <div class="circle" :class="form.gender == 1 ? 'active' : '' " @click="chooseGender(1)">
                <svg style="width: 45px; height: 45px" viewBox="0 0 24 24">
                  <path
                    fill="currentColor"
                    d="M12,4A6,6 0 0,1 18,10C18,12.97 15.84,15.44 13,15.92V18H15V20H13V22H11V20H9V18H11V15.92C8.16,15.44 6,12.97 6,10A6,6 0 0,1 12,4M12,6A4,4 0 0,0 8,10A4,4 0 0,0 12,14A4,4 0 0,0 16,10A4,4 0 0,0 12,6Z"
                  />
                </svg>
              </div>
              <p>Female</p>
              <div class="circle" :class="form.gender == 2 ? 'active' : '' " @click="chooseGender(2)">
                <svg style="width: 45px; height: 45px" viewBox="0 0 24 24">
                  <path
                    fill="currentColor"
                    d="M9,9C10.29,9 11.5,9.41 12.47,10.11L17.58,5H13V3H21V11H19V6.41L13.89,11.5C14.59,12.5 15,13.7 15,15A6,6 0 0,1 9,21A6,6 0 0,1 3,15A6,6 0 0,1 9,9M9,11A4,4 0 0,0 5,15A4,4 0 0,0 9,19A4,4 0 0,0 13,15A4,4 0 0,0 9,11Z"
                  />
                </svg>
              </div>
              <p>Male</p>
            </div>
            <v-btn rounded color="primary" dark class="w-100 mt-10 my-btn" @click="next"> NEXT </v-btn>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data () {
    return {
      form: {
        firstname: ' ',
        lastname: ' ',
        gender: 1
      }
    }
  },
  methods: {
    chooseGender (gender) {
      this.form.gender = gender
    },
    next () {
      this.$router.push('/register/step2')
    }
  }
}
</script>

<style lang="scss" scoped>
.v-form {
  padding: 0 10px;
}

.gender-group {
  p {
    margin-bottom: 0;
    align-self: center;
    margin-right: 20px;
  }
  .circle {
    width: 45px;
    height: 45px;
    color: #fff;
    border-radius: 50%;
    margin-right: 7px;
    background: rgba($color: #000, $alpha: 0.3);
    &.active {
      background: #1a56be;
    }
     position: relative;
     svg{
         align-content: center;
         padding: 5px 5px 5px 5px;
     }
  }
}
</style>
