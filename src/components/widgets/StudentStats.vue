<template>
  <WidgetContainer title="Student Stats">
    <div class="grid pt-3">
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[0]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          :readonly="true"
        />
        <p class="text-center text-lg">Perfect Scores</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[1]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          valueColor="#1abc78"
          :readonly="true"
        />
        <p class="text-center text-lg">Consistency</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[2]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          :readonly="true"
          valueColor="#f05437"
        />
        <p class="text-center text-lg">Did Not Pass</p>
      </div>
      <div class="col-6 flex flex-column align-items-center">
        <Knob
          v-model="knobValue[3]"
          :step="10"
          :max="100"
          valueTemplate="{value}%"
          :readonly="true"
          valueColor="#1abc78"
        />
        <p class="text-center text-lg">Participation</p>
      </div>
    </div>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '@/components/WidgetContainer.vue';

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
