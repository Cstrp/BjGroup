<script>
export default {
  props: ['text'],
};
</script>
<template>
  <div class="divider__container">
    <div class="divider__wrapper">
      <div class="divider" />
      <div class="divider__title">
        <v-tooltip :text="text" location="bottom">
          <template v-slot:activator="{ props }">
            <div v-bind="props" class="divider__text">
              {{ text }}
            </div>
          </template>
        </v-tooltip>
      </div>
      <div class="divider" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.divider__wrapper {
  display: flex;
  align-items: center;
  gap: 22px;
  margin-bottom: 60px;

  .divider {
    width: 100%;
    height: 2px;
    background-color: #1e1e1e;
    flex: 1 1 auto;
  }
}

.divider__title {
  flex: 1 0 auto;
  padding: 15px 40px;
  border: 2px #1e1e1e solid;
  border-radius: 20px;
  text-align: center;

  @media (max-width: 991.98px) {
    font-size: 18px;
    line-height: 22px;
    padding: 10px 25px;
  }

  @media (max-width: 767.98px) {
    font-size: 15px;
  }

  .divider__text {
    font-size: 23px;
    font-weight: 600;
    line-height: 27px;

    @media (max-width: 991.98px) {
      font-size: 18px;
    }

    @media (max-width: 767.98px) {
      font-size: 15px;
    }
  }
}
</style>
