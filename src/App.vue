<script setup>
    const modalConfirm = () => {
      console.log('modal confirm');
    }

    const modalClose = () => {
      console.log('modal close');
    }
</script>

<template>
  <Modal
    :show="true"
    :width="350"
    :borderRadius="10"
    headerColor="'#333'"
    headerTextColor="#fff"
    headerText="Modal Header"
    contentText="lorem ipsum dolor sit amet, consectetur adipiscing elit."
    contentTextColor="#333"
    position="center"
    :buttonGroupShow="true"
    confirmText="是"
    cancelText="否"
    @confirm="modalConfirm"
    @close="modalClose"
  />
</template>

<style scoped>

</style>
