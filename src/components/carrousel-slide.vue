<template>
    <transition :name="slideDirection">
        <div v-show="visible" style="width: 100%;">
            <slot>
            </slot>
        </div>
    </transition>
</template>

<script>
export default {
    data() {
        return {
            index: 0
        }
    },
    computed: {
        visible() {
            return this.index === this.$parent.index
        },
        slideDirection() {
            return `slide${this.$parent.direction}`
        }
    }
}
</script>

<style lang="scss">
.slideRight-enter-active {
    animation: slideRightInAppear .2s ease-in-out;
}
.slideRight-leave-active {
    animation: slideRightOutAppear .2s ease-in-out;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}
@keyframes slideRightInAppear {
    0% {
        transform: translateX(100%);
    }
    100% {
        transform: translateX(0);
    }
}
@keyframes slideRightOutAppear {
    0% {
        transform: translateX(0%);
    }
    100% {
        transform: translateX(-100%);
    }
}
.slideLeft-enter-active {
    animation: slideLeftInAppear .2s ease-in-out;
}
.slideLeft-leave-active {
    animation: slideLeftOutAppear .2s ease-in-out;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}
@keyframes slideLeftInAppear {
    0% {
        transform: translateX(-100%);
    }
    100% {
        transform: translateX(0);
    }
}
@keyframes slideLeftOutAppear {
    0% {
        transform: translateX(0%);
    }
    100% {
        transform: translateX(100%);
    }
}

</style>
