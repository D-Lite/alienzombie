<template>
    <div class="modal">
        <div class="modal-inner">
            <h1 v-if="uiState === 'won'">You Won!</h1>
            <h1 v-else>You Lost!</h1>
       
            <img 
                src="./../assets/face.svg" 
                alt=""
                :class=" uiState === 'won' ? 'smille' : 'quarrel'  "    
            >

            <!-- <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 131 131"
                aria-labelledby="face"
                role="presentation"
                width="70"
                height="70"
                >
                <title id="face">Face Icon</title>
                <defs>
                </defs>
                <circle class="cls-1" cx="65.5" cy="65.5" r="64" />
                <circle class="cls-2" cx="95" cy="65.8" r="7.5" />
                <circle class="cls-2" cx="36" cy="65.8" r="7.5" />
                <path
                    class="cls3"
                    :class=" uiState === 'won' ? 'smile' : 'quarrel' "
                    d="M51,97s6,10,23,10S95,97,95,97"
                    transform="translate(-8.5 -5.5)"
                />
            </svg> -->

        </div>

        <button @click="restartGame"> Let's Play Again! </button>

        <slot></slot>
    </div>
</template>

<script>
    import { mapState } from 'vuex';
    
    export default {
        computed: {
            ...mapState([
                'uiState',
            ])
        },
        methods: {
            restartGame() {
                this.$store.commit("restartGame");
            }
        }
    };

</script>

<style lang="scss" scoped>
    .modal {
        padding: 40px 100px 40px 100px;
    }

    .quarrel {
        transform: rotate(180deg);
    }

    .modal-inner {
        display: flex;
        align-content: center;
        justify-content: center;
        flex-direction: column;
    }

        .cls-1 {
      fill: #fbb040;
      stroke: #231f20;
      }

      .cls-1,
      .cls-3 {
      stroke-miterlimit: 10;
      stroke-width: 3px;
      }

      .cls-2 {
      fill: #231f20;
      }

      .cls-3 {
      fill: none;
      stroke: #be1e2d;
      }
</style>