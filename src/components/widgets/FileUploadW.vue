<template>
  <WidgetContainer title="File Upload">
    <div class="file-upload pt-2 pb-3 w-full">
      <FileUpload
        name="files[]"
        url="./upload"
        :multiple="true"
        :maxFileSize="1000000"
      >
        <template #empty>
          <p>Drag and drop files to here to upload.</p>
        </template>
      </FileUpload>
    </div>
  </WidgetContainer>
</template>

<script>
import WidgetContainer from '@/components/WidgetContainer.vue';

export default {
  components: {
    WidgetContainer,
  },
};
</script>

<style></style>
