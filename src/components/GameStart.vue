<template>
    <div :class="`banner ${ isVisible ? 'visible': '' }`">
        <div class="tictactoe-container">
            <div class="banner__title">
            <div class="text__setup">
                Welcome to <span>TIC TAC TOE</span>
            </div>
            </div>
            <div class="text__play" @click="$emit('click:play')">
                <button class="attribute__button">PLAY</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        isVisible: {
            type: Boolean,
            default: true,
        },
    }
}
</script>
<style lang="scss" scoped>


.banner {
    position: absolute;
    top: -100%;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 11;
    background:#0B233F;
    transition: top 1s;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.visible {
    top: 0;
    transition: top 1s;
}

</style>