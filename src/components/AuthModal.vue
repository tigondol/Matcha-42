<template>
    <div className="auth-modal">
        <div className="close-icon" @click="handleClick">ⓧ</div>

        <h2>{{ isSignUp ? 'CREATE ACCOUNT': 'LOG IN' }}</h2>
        <p>By clicking Log In, you agree to our terms. Learn how we process your data in our Privacy Policy and Cookie Policy.</p>
        <form onsubmit="() => console.log('hi')">
            <input
                type="email"
                id="email"
                name="email"
                placeholder="email"
            />
            <input
                type="password"
                id="password"
                name="password"
                placeholder="password"
            />
            <input
                v-if="isSignUp"
                type="password"
                id="password-check"
                name="password-check"
                placeholder="confirm password"
            />
            <input className="secondary-button" type="submit"/>
            <p>{{error}}</p>
        </form>

        <hr/>
        <h2>GET THE APP</h2>

    </div>
</template>

<script>

export default {
    name: 'AuthModal',
    props: {
        isSignUp: false,
    },
    methods: {
        handleClick() {
            this.$emit('closeModal');
        },
    }
};
</script>