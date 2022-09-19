<template>
  <WidgetContainer title="Student Stats">
    <div class="grid pt-3">
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[0]"
          :step="10"
          :max="100"
          valueColor="#00bfff"
          rangeColor="#00bfff30"
          valueTemplate="{value}%"
          :readonly="true"
        />
        <p class="text-center text-lg rhythm">Perfect Scores</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[1]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          valueColor="#6BD425"
          rangeColor="#6BD42530"
          :readonly="true"
        />
        <p class="text-center text-lg rhythm">Consistency</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[2]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          :readonly="true"
          valueColor="#ED254E"
          rangeColor="#ED254E30"
        />
        <p class="text-center text-lg rhythm">Did Not Pass</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[3]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          :readonly="true"
          valueColor="#6BD425"
          rangeColor="#6BD42530"
        />
        <p class="text-center text-lg rhythm">Participation</p>
      </div>
    </div>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    WidgetContainer
  },
  data() {
    return {
      knobValue: [54, 73, 27, 96],
    };
  },
};
</script>

<style></style>
