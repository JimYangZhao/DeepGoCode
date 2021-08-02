<template>
  <div class="leftpadding">
    <h3><font-awesome-icon :icon="myIcon" /> Create Your NudgePool</h3>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faArrowLeft } from '@fortawesome/free-solid-svg-icons';

export default {
  name: 'MyComponent',

  data() {
    return {
      myIcon: faArrowLeft,
    };
  },

  components: {
    FontAwesomeIcon,
  },
};
</script>
<style>
.leftpadding {
  padding: 24px 24px 16px;
}
</style>
