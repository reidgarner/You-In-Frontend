<template>
    <view class="container">
        <text class="title">You In?</text>
        <text class="As-a">Login as a</text>
        <touchable-opacity class="button-1" :on-press="handleGuestLogin">
            <text class="button-text">Bar Guest</text>
        </touchable-opacity>
        <text class="Or">Or a</text>
        <touchable-opacity class="button-2" :on-press="handleBTLogin">
            <text class="button-text">Bartender</text>
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
        handleGuestLogin() {
            this.navigation.navigate("GuestLogin");
        },
        handleBTLogin() {
            this.navigation.navigate("BTLogin");
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
    width: 250;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-2 {
    background-color: rgb(67, 67, 67);
    width: 250;
    height: 100;
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

.As-a {
    color: black;
    font-size: 40;
    position: relative; top: 30;
    font-family: Courier;
}

.Or {
    color: black;
    font-size: 40;
    position: relative; top: 60;
    font-family: Courier;
}
</style>