<template>
  <WidgetContainer title="File Upload">
    <div class="file-upload py-2 w-full">
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
import WidgetContainer from '../WidgetContainer.vue';

export default {
  components: {
    WidgetContainer,
  },
};
</script>

<style></style>
