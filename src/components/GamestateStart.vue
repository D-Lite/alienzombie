<template>
    <div class="modal">
        <h1 id="header">You're an alienzombie.</h1>
        <p>
            In order to survive on Earth, you have to pretend to be a human on this
            planet. You took over the body of a nearby hooman, but the trouble is, their
            best friend showed up!
        </p>
        <p>
            They look suspicious. Answer the questions right to make sure identity is
            kept secret!

            **Best optimized for desktop view**
        </p>
        <slot></slot>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    @media only screen and  (max-width: 500px) {
        .modal {
            width: 150px;
            font-size: 10px;
            margin-left: 150px;
        }
    }
</style>