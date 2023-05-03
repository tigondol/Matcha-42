<template>
    <nav>
        <div className="logo-container">
            <img className="logo" src="../images/color-logo-tinder.png">
        </div>
        <button v-if="!authToken && !minimal" className="nav-button" @click="handleClick">Log in</button>
    </nav>
</template>

<script>
export default {
    name: 'Navbar',
    props: {
        minimal: false,
        authToken: null,
    },
    data() {
    },
    computed: {
    },
    methods: {
        handleClick() {
            this.$emit('loginClick')
        },
    }
};
</script>