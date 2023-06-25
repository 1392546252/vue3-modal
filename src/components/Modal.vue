<template>

</template>

<script setup>
    
    // 用diefineProps定义props
    defineProps({
        show: {
            type: Boolean,
            default: false,
        },
        width: {
            type: Number,
            default: 300,
        },
        borderRadius: {
            type: Number,
            default: 0,
        },
        headerColor: {
            type: String,
            default: '#000',
        },
        headerTextColor: {
            type: String,
            default: '#fff',
        },
        headerText: {
            type: String,
            default: 'modal',
        },
        contentText: {
            type: String,
            default: '',
        },
        contentTextColor: {
            type: String,
            default: '#000',
        },
        position: {
            type: String,
            default: 'top',
        },
        buttonGroupShow: {
            type: Boolean,
            default: false,
        },
        confirmText: {
            type: String,
            default: 'confirm',
        },
        cancelText: {
            type: String,
            default: 'cancel',
        },
    })

    // 用defineEmits定义事件
    const emits = defineEmits(['confirm', 'close'])

    const modalConfirm = () => {
        console.log('modal confirm');
        // 触发事件
        emit('confirm')
    }

    const modalClose = () => {
        console.log('modal close');
        // 触发事件
        emit('close')
    }


</script>

<style scoped>

</style>