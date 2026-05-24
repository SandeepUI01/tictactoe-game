<template>
    <div :class="`cell ${ isHighlighted ? 'highlight': '' }`" @click="$emit('click:action')" :style="`width: ${ 100 / gridSize }%; height: ${ 100 / gridSize }%;`">
        <i v-if="sign == 'x'" class="sign sign__x">x</i>
        <i v-else-if="sign == 'o'" class="sign sign__o">0</i>
    </div>
</template>
<script>
export default {
    props: {
        gridSize: {
            type: [String, Number],
            default: '3',
        },
        sign: {
            type: [String, Number],
            default: '',
        },
        cellPosition: {
            type: [String, Number],
        },
        isHighlighted: {
            type: Boolean,
            default: false,
        }
    }
}
</script>
