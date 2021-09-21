<template>
  <div @pointerup="selectFolder" @dblclick="selectFolder" @mousedown.prevent class="folder">
    <div class="folder__content">
      <div class="folder__image">
        <img src="../../public/svg/folder-icon2.svg" />
      </div>
      <p class="folder__name">
        {{ name }}
      </p>
    </div>
    <div class="folder__info">
      <span>Файлов: {{ amountFiles }}</span>
      <span> Папок: {{ amountFolders }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "FolderView",
  props: {
    name: String,
    index: Number,
    amountFolders: Number,
    amountFiles: Number,
  },

  methods: {
    selectFolder(event) {
      if (event.type === 'pointerup' && window.innerWidth >1024) return;
      this.$emit("open", this.index);
    },
  },
};
</script>

