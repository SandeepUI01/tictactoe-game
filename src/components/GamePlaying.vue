<template>
    <div class="player-monitor">
        <div :class="`static-box ${ activePlayer == 'player1' ? 'highlight-player': '' }`">
            <small>Player 1</small>
            <p class="text__setup">{{ player1Name }}</p>
            <i class="sign sign__x smallIcon">0</i>
        </div>
        <div :class="`static-box ${ activePlayer == 'player1' ? '': 'highlight-player' }`">
            <small>Player 2</small>
            <p class="text__setup">{{ player2Name }}</p>
            <i class="sign sign__o smallIcon">x</i>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        player1Name: {
            type: String,
            default: 'Player1',
        },
        player2Name: {
            type: String,
            default: 'Player2',
        },
        activePlayer: {
            type: String,
            default: 'player1',
        },
    },
    methods: {
        toggleMovingBox() {

        }
    },
}
</script>
