<template>
  <v-stepper v-model="e13" vertical>
    <!-- Step #1   -->
    <v-stepper-step :complete="e13 > 1" step="1">
      Basics
    </v-stepper-step>
    <v-stepper-content step="1">
      <v-card color="lighten-1">
        <BasicsForm />
        <v-btn color="primary" @click="e13 = 2">
          Next
        </v-btn>
      </v-card>
    </v-stepper-content>
    <!-- Step #2 -->
    <v-stepper-step :complete="e13 > 2" step="2">
      Collateral Settings
    </v-stepper-step>
    <v-stepper-content step="2">
      <v-card color="lighten-1" class="mb-12">
        <CollateralForm />
      </v-card>
      <v-btn text @click="e13 = 1">
        Previous
      </v-btn>
      <v-btn color="primary" @click="e13 = 3">
        Next
      </v-btn>
    </v-stepper-content>
    <!-- Step #3 -->
    <v-stepper-step :complete="e13 > 3" step="3">
      Charge Settings
    </v-stepper-step>
    <v-stepper-content step="3">
      <v-card color="lighten-1" class="mb-12">
        <ChargeSetting />
      </v-card>
      <v-btn text @click="e13 = 1">
        Previous
      </v-btn>
      <v-btn color="primary" @click="e13 = 4">
        Next
      </v-btn>
    </v-stepper-content>
    <!-- Step #4 -->
    <v-stepper-step :complete="e13 > 4" step="4">
      Pool Construction Period
    </v-stepper-step>
    <v-stepper-content step="4">
      <v-card color="lighten-1" class="mb-12">
        <PoolDuration />
      </v-card>
      <v-btn text @click="e13 = 3">
        Previous
      </v-btn>
      <v-btn color="primary" @click="e13 = 5">
        Next
      </v-btn>
    </v-stepper-content>
    <!-- Step #5 -->

    <v-stepper-step step="5">
      Reviews
    </v-stepper-step>
    <v-stepper-content step="5">
      <v-card color="lighten-1" class="mb-12">
        <Reviews />
      </v-card>
      <v-btn color="primary" @click="e13 = 1">
        Return to Basics
      </v-btn>
    </v-stepper-content>
  </v-stepper>
</template>

<script>
import BasicsForm from './../components/Forms/BasicsForm';
import CollateralForm from './../components/Forms/CollateralForm';
import ChargeSetting from './../components/Forms/ChargeSetting';
import PoolDuration from './../components/Forms/PoolDuration';
import Reviews from './../components/Forms/Reviews';

export default {
  components: {
    BasicsForm,
    CollateralForm,
    ChargeSetting,
    PoolDuration,
    Reviews,
  },
  data() {
    return {
      e13: 1,
    };
  },
};
</script>
