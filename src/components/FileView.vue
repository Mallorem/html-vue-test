<template>
  <div class="file">
    <img src="../images/file.svg" alt="file icon" class="file__icon" />
    <p class="file__name">{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: "FileView",
  props: {
    name: String,
  },
};
</script>

<style scoped lang="scss">
.file {
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

  &__icon {
    -webkit-box-flex: 0;
    -ms-flex: 0 0 35px;
    flex: 0 0 35px;
    margin-right: 20px;
  }

  &:hover {
    -webkit-transform: scale(1.01);
    -ms-transform: scale(1.01);
    transform: scale(1.01);
    -webkit-box-shadow: 0px 0px 33px 0px rgba(0, 1, 25, 0.2);
    box-shadow: 0px 0px 33px 0px rgba(0, 1, 25, 0.2);
  }
}
</style>
