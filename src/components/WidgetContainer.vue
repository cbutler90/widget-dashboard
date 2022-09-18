<template>
  <Card class="border-round-md raisin-black-bg">
    <template #header>
      <Toolbar>
        <template #start>
          <h1 class="widget-title text-base casper">{{ title }}</h1>
        </template>

        <template #end>
          <Button icon="pi pi-ellipsis-v" class="mr-2" />
          <Button icon="pi pi-times" class="ml-1" />
        </template>
      </Toolbar>
    </template>
    <template #content>
      <slot class="p-3"></slot>>
    </template>
  </Card>
</template>

<script>
export default {
  props: [ 'title' ]
};
</script>

<style></style>
