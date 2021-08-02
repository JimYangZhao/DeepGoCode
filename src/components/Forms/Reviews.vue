<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <div class="title">Reviews<br /></div>
    <p>Please check all your settings.</p>

    <!-- Show all data-->
    <template>
      <v-card>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Token Name </v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item two-line>
          <v-list-item-content>
            <v-list-item-title>Denomination Asset</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item three-line>
          <v-list-item-content>
            <v-list-item-title>Project Website</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item four-line>
          <v-list-item-content>
            <v-list-item-title>Tokens impawned</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item five-line>
          <v-list-item-content>
            <v-list-item-title>LTV</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item six-line>
          <v-list-item-content>
            <v-list-item-title>Liquidation LTV</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item seven-line>
          <v-list-item-content>
            <v-list-item-title>Charge Rate</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-list-item eight-line>
          <v-list-item-content>
            <v-list-item-title>(Pool) Construction Period</v-list-item-title>
            <v-list-item-subtitle>Data</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-card>
    </template>

    <v-checkbox v-model="checkbox">
      <template v-slot:label>
        <div>
          I agree to the
          <v-tooltip bottom>
            <template v-slot:activator="{ on }">
              <a
                target="_blank"
                href="https://vuetifyjs.com"
                @click.stop
                v-on="on"
              >
                Terms & Conditions.
              </a>
            </template>
          </v-tooltip>
        </div>
      </template>
    </v-checkbox>
    <v-btn color="success" class="mr-4" @click="snackbar = true">
      Confirm
    </v-btn>
    <v-snackbar v-model="snackbar" :timeout="timeout">
      {{ text }}

      <template v-slot:action="{ attrs }">
        <v-btn color="blue" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
  </v-form>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    checkbox: false,
    snackbar: false,
    text: 'You have submitted successful! Thank you.',
    timeout: 2000,
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
  },
};
</script>
