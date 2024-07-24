<template>
  <div>
    <template v-if="item?.render && typeof item?.render === 'function'">
      <component
        :is="renderContent(item, form)"
        v-if="isVNode(renderContent(item, form))"
      />
      <span v-else v-html="renderContent(item, form)" />
    </template>
  </div>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    required: true,
  },
  form: {
    type: Object,
    required: true,
  },
});
function isVNode(value) {
  return value && typeof value === "object" && value.__v_isVNode;
}

function renderContent(item, detailData) {
  return item?.render({
    record: detailData,
  });
}
</script>

<style lang="scss" scoped></style>
