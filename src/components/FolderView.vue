<template>
  <div class="folder">
    <div class="folder__info" @click="toggleFolder">
      <img src="../images/folder.svg" alt="folder icon" class="folder__icon" />
      <p class="folder__name">{{ name }}</p>
    </div>

    <div
      class="folder__child"
      v-for="(folder, index) in folders"
      v-bind:key="index"
    >
      <FolderView
        :name="folder.name"
        :folders="folder.folders"
        :files="folder.files"
        v-if="opened"
      />
    </div>

    <div
      class="folder__child"
      v-for="(file, index) in files"
      v-bind:key="index"
    >
      <FileView :name="file.name" v-if="opened" />
    </div>
  </div>
</template>

<script>
import FileView from "./FileView";
export default {
  name: "FolderView",
  data() {
    return { opened: false };
  },
  components: { FileView },
  props: {
    name: String,
    folders: Array,
    files: Array,
  },
  methods: {
    toggleFolder() {
      this.opened = !this.opened;
    },
  },
};
</script>

<style scoped lang="scss">
.folder {
  &__info {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    background-color: #f8f8f8;
    min-height: 60px;
    border-radius: 20px;
    padding: 20px;
    margin-bottom: 20px;
    color: #000119;
    font-size: 15px;
    line-height: 19px;
    font-weight: bold;
    -webkit-transition: all 0.3s ease-in-out;
    -o-transition: all 0.3s ease-in-out;
    transition: all 0.3s ease-in-out;
    cursor: pointer;

    &:hover {
      -webkit-transform: scale(1.01);
      -ms-transform: scale(1.01);
      transform: scale(1.01);
      -webkit-box-shadow: 0px 0px 33px 0px rgba(0, 1, 25, 0.2);
      box-shadow: 0px 0px 33px 0px rgba(0, 1, 25, 0.2);
    }
  }

  &__icon {
    -webkit-box-flex: 0;
    -ms-flex: 0 0 50px;
    flex: 0 0 50px;
    margin-right: 20px;
  }

  &__child {
    margin-left: 30px;

    @media screen and (max-width: 768px) {
      margin-left: 20px;
    }
  }
}
</style>
