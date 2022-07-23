<template>
  <div>
    <v-container>
      <v-row>
        <v-col>
          <v-form ref="signUpForm" v-model="isValidForm">
            <v-text-field
              type="Email"
              label="email"
              v-model="model.email"
              required
              :rules="emailRules"
              validate-on-blur
            />
            <v-autocomplete
              label="Wich browser do you use?"
              :items="browsers"
              v-model="model.browser"
            />
            <v-file-input label="Attach profile photo" v-model="model.photo" />
            <v-text-field label="Birthday" v-model="model.birthday" readonly />
            <v-date-picker v-model="model.birthday" />
            <v-checkbox
              v-model="model.agree"
              label="Agree to terms & conditions"
              required
              :rules="agreeTermsRules"
              validate-on-blur
            />
            <v-btn type="submit" color="primary">Submit</v-btn>
            <v-btn @click="validate">Validate</v-btn>
            <v-btn @click="resetValidation">Reset Validation</v-btn>
            <v-btn @click="resetForm">Reset Form</v-btn>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      model: {},
      isValidForm: false,
      emailRules: [
        (value) => !!value || "Email is required",
        (value) =>
          (!!value &&
            !!value.match(/[^@ \t\r\n]+@[^@ \t\r\n]+\.[^@ \t\r\n]+/)) ||
          `${value} is not a valid email`,
      ],
      agreeTermsRules: [
        (value) => !!value || "You must to agree the terms to sign up",
      ],
      browsers: ["Chrome", "Firefox", "Safari", "Edge", "Brave"],
    };
  },
  methods: {
    resetForm() {
      this.$refs.signUpForm.reset();
    },
    resetValidation() {
      this.$refs.signUpForm.resetValidation();
    },
    validate() {
      this.$refs.signUpForm.validate();
    },
  },
};
</script>
