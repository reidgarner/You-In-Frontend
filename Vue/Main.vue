<template>
    <view class="container">
        <status-bar :barStyle="'dark-content'"></status-bar>
        <image-background :source="bartenderImg" class="imageContainer">
            <image :source="logo" class="logo"></image>
            <touchable-opacity class="button-1" :on-press="handleLogin">
                <text class="button-text">Login</text>
            </touchable-opacity>
            <touchable-opacity class="button-2" :on-press="handleSignup">
                <text class="button-text">Sign Up</text>
            </touchable-opacity>
        </image-background>
    </view>
</template>

<script>
import bartenderImg from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/bartender-opacified-2.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/Logo.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            logo: logo,
            bartenderImg: bartenderImg,
            statusBar: {
                backgroundColor: 'black'
                }
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
.imageContainer {
    flex: 1;
    align-items: center;
    justify-content: center;
    width: 130%;
    /* opacity: .8; */
    position: relative; left: 50;
}

.container {
    background-color: white;
    align-items: center;
    justify-content: center;
    flex: 1;
}

.logo {
    height: 25%;
    width: 40%;
    position: relative; bottom: 190; right: 135;
    border-radius: 7;
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

.status-bar{
    background-color: black;
}
</style>
