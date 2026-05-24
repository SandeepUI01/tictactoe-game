<template>
    <div :class="`banner ${ isVisible ? 'visible': '' }`">
        <div class="tictactoe-container">
            <div class="banner__title" style="text-align: center;">
            <div class="text__setup">
        <div v-if="hasWinner" class="">
            <span>Congrates &#128077;</span>
        </div>
        <div v-else class="">
            <span>It's a tie</span>
        </div>
        <div>
            <p v-if="hasWinner" class="text__endgame"><span>{{ playerName }}</span> won!</p>
            <p v-else class="text__endgame">Nobody won! Try again?</p>
        </div>
        
        <button class="attribute__button" @click="$emit('click:replay')" style="margin-top:100px">PLAY AGAIN</button>
    </div>
</div>
</div>
</div>
</template>
<script>
export default {
    props: {
        isVisible: {
            type: Boolean,
            default: false,
        },
        hasWinner: {
            type: Boolean,
            default: false,
        },
        playerName: {
            type: String,
            default: '',
        },
    },
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
    animation-name: scrolling;
    animation-duration: 2s;
    top: 0;
    transition: top 1s;
}
.attribute {
    &__button {
        margin-top: 20px;
        animation: appear 3s ease-in-out;
    }
}
</style>