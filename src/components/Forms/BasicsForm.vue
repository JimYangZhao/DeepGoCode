<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <div class="title">Basics</div>
    <p>
      Basic NudgePool settings.
      <strong>Basic setting cannot be changed after creation.</strong>
    </p>
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Token Name(10 digital number)"
      placeholder="123 456 7890"
      required
    ></v-text-field>

    <v-select
      v-model="select"
      :items="items"
      :rules="[(v) => !!v || 'Selection is required']"
      label="Denomination Assets"
      placeholder="BTC"
      required
    ></v-select>

    <v-text-field
      v-model="website"
      :rules="websiteRules"
      label="Project Website"
      placeholder="www.xxxxx.com"
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
    name: '',
    nameRules: [
      (v) => !!v || 'Token Name is required',
      (v) => (v && v.length == 10) || 'Token Name must be 10 characters',
    ],
    website: '',
    websiteRules: [(v) => !!v || 'Project Website is required'],

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
