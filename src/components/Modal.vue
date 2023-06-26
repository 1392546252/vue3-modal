<template>
    <div
        class="modal-mask"
        v-show="show">
        <div
            class="ui-modal"
        >
            <header class="header">
                <h1>{{ headerText }}</h1>
                <a href="javascript:;">&times;</a>
            </header>
            <article class="content">
                <p>{{ contentText }}</p>
            </article>
            <div 
                class="btn-group"
                v-if="btnGroupShow">
                <button class="btn btn-confirm">{{ confirmText }}</button>
                <button class="btn btn-cancel">{{ cancelText }}</button>
            </div>
        </div>
    </div>
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
            default: 'modal content modal content',
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
        btnGroupShow: {
            type: Boolean,
            default: true,
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
    .modal-mask {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(0,0,0,.5);
    }
    .ui-modal {
            position:fixed;
            left: 50%;
            overflow: hidden;
            background-color: #fff;
        }
</style>