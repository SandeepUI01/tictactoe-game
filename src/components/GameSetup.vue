<template>
    <div :class="`banner ${ isVisible ? 'visible': '' }`">
        <div class="tictactoe-container">
        <div class="banner__title">
            <div class="text__setup">
                Welcome to <span>TIC TAC TOE</span>
            </div>
            <div class="settings">
                <div class="attribute">
                    <p class="attribute__text">player 1 </p>
                    <input class="attribute__text-input" v-model="settings.player1Name" type="text" placeholder="Player 1 Name" maxlength="10"/>
                </div>
                <div class="attribute">
                    <p class="attribute__text">player 2 </p>
                    <input class="attribute__text-input" v-model="settings.player2Name" type="text" placeholder="Player 2 Name" maxlength="10"/>
                </div>
                
                <div class="attribute">
                    <p class="attribute__text">Starting player </p>
                    <div class="attribute__text-radio">
                       <div class="playerSelect">
                        <input class="attribute__text-radio-input" v-model="settings.startingPlayer" type="radio" id="player1" name="starting-player" value="player1">
                        <label class="attribute__text-radio-label" for="player1" >{{settings.player1Name}}</label>
                       </div>
                       <div class="playerSelect">
                        <input class="attribute__text-radio-input" v-model="settings.startingPlayer" type="radio" id="player2" name="starting-player" value="player2">
                        <label class="attribute__text-radio-label" for="player2">{{settings.player2Name}}</label>
                    </div>
                    </div>
                </div>
                

                <button class="attribute__button" @click="validateFields">START</button>
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
    },
    data() {
        return {
            settings: {
                player1Name: '',
                player2Name: '',              
                startingPlayer: '',
                gridSize: '3',
            },
        }
    },
    methods: {
        validateFields() {
            let validationPassed = true;
            for (let setting in this.settings) {
                if (this.settings[setting] == '') {
                    validationPassed = false;
                    break;
                }
            }
            if (!validationPassed) return;
            return this.$emit('click:start', this.settings);
        }
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
.settings {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
</style>