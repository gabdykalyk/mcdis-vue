<template>
  <div class="file">
    <div class="file__content">
      <div class="file__image">
        <img v-if="type == 'image/svg'" src="../../public/svg/svg-icon.svg" />
        <img
          v-else-if="type == 'image/jpeg'"
          src="../../public/svg/jpeg-icon.svg"
        />
        <img
          v-else-if="type == 'image/png'"
          src="../../public/svg/png-icon.svg"
        />
        <img
          v-else-if="type == 'application/javascript'"
          src="../../public/svg/js-icon.svg"
        />
        <img v-else src="../../public/svg/icons8-file.svg" />
      </div>
      <p class="file__name">{{ name }}<br /></p>
    </div>
    <div class="file__info">
      <span>Тип: {{ type }}</span>
      <span> Количество символов: {{ length }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "FileView",
  props: {
    name: String,
    type: String,
    length: String
  },

  created() {},
};
</script>

