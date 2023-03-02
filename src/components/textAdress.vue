<template>
  <p v-if="text"><span class="label-text">Адрес доставки</span>{{ text }}</p>
</template>

<script>
export default {
  props: ["text"],
  // props: {
  //   text: {
  //     type: string,
  //     required: false,
  //   },
  // },
};
</script>