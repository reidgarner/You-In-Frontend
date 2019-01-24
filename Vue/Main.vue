<template>
    <view class="container">
        <text class="title">You In?</text>
        <touchable-opacity class="button-1" :on-press="handleLogin">
            <text class="button-text">Login</text>
        </touchable-opacity>
        <touchable-opacity class="button-2" :on-press="handleSignup">
            <text class="button-text">Sign Up</text>
        </touchable-opacity>
    </view>
</template>

<script>
export default {
    props: {
        navigation: {
            type: Object
        }
    },

    methods: {
        handleLogin() {
            this.navigation.navigate("Login");
        },
        handleSignup() {
            this.navigation.navigate("Signup");
        }
    }
}
</script>

<style>
.container {
    background-color: white;
    align-items: center;
    justify-content: center;
    flex: 1;
}
.title {
    color: black;
    font-size: 50;
    position: relative; bottom: 150;
    font-family: Courier;
}

.button-1 {
    background-color: rgb(67, 67, 67);
    width: 200;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-2 {
    background-color: rgb(67, 67, 67);
    width: 200;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 80;
}

.button-text {
    color: rgb(159, 159, 159);
    font-size: 40;
    font-family: Courier;
}
</style>
