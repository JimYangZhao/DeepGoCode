<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <div class="title">Charge Settings</div>
    <p>
      Please set up your token amount and impawn rate. These parameters will
      determine your total GP fundraising amount.
    </p>
    <v-text-field
      v-model="chargeRate"
      :rules="chargeRateRules"
      label="Charge Rate"
      placeholder="5%"
      required
    ></v-text-field>

    <!-- 可以加一个防spam checkbox, like recaptcha-->

    <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
      Next
    </v-btn>

    <!-- <v-btn color="error" class="mr-4" @click="reset">
      Reset Form
    </v-btn>

    <v-btn color="warning" @click="resetValidation">
      Reset Validation
    </v-btn> -->
  </v-form>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    chargeRate: '',
    chargeRateRules: [
      (v) => !!v || 'Charge Rate is required',
      (v) => (v && v.length <= 10) || 'Charge Rate must be a percentage.',
    ],
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    select: null,
    items: ['BTC', 'ETH', 'BNB', 'USDT'],
    checkbox: false,
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    // reset() {
    //   this.$refs.form.reset();
    // },
    // resetValidation() {
    //   this.$refs.form.resetValidation();
    // },
  },
};
</script>
