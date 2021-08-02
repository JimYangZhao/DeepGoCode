<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <div class="title">Collateral Settings</div>
    <p>
      Please set up your token amount and impawn rate. These parameters will
      determine your total GP fundraising amount.
    </p>
    <v-text-field
      v-model="tokenImpawned"
      :rules="tokenImpawnedRules"
      label="Token Impawned"
      placeholder="1,000,000,000"
      required
    ></v-text-field>

    <v-text-field
      v-model="ltv"
      :rules="LTVRules"
      label="LTV"
      placeholder="30%"
      required
    ></v-text-field>

    <v-text-field
      v-model="lqltv"
      :rules="LQLTVRules"
      label="Liquidation LTV"
      placeholder="50%"
      required
    ></v-text-field>

    <!-- 可以加一个防spam checkbox， like recaptcha-->

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
    tokenImpawned: '',
    tokenImpawnedRules: [(v) => !!v || 'Token Impawned is required'],
    ltv: '',
    LTVRules: [(v) => !!v || 'LTV is required'],
    lqltv: '',
    LQLTVRules: [(v) => !!v || 'Liquidation LTV is required'],
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
