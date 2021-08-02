<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <div class="title">Pool Duration<br /></div>
    <p>
      Please enter the duration of the pool. <br />
      Notice 1: The starting date is 7 days from today. <br />
      Notice 2: From today to the starting point, any participant that meets the
      criteria could bid for the initiating right. <br />
      Notice 3: This duration should be over 90 days.<br />
    </p>
    <v-text-field
      v-model="Duration"
      :rules="DurationRules"
      label="Duration"
      placeholder="180 days"
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
    Duration: '',
    DurationRules: [(v) => !!v || 'Duration time is required'],
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
