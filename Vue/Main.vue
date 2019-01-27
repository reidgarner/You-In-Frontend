<template>
    <view class="container">
        <status-bar :barStyle="'dark-content'"></status-bar>
        <image-background :source="bartenderImg" class="imageContainer">
            <image :source="logo" class="logo"></image>
            <view class="button-container">
                <touchable-opacity class="button-1" :on-press="handleLogin">
                    <text class="button-text">Login</text>
                </touchable-opacity>
                <touchable-opacity class="button-2" :on-press="handleSignup">
                    <text class="button-text">Sign Up</text>
                </touchable-opacity>
            </view>
        </image-background>
    </view>
</template>

<script>
import bartenderImg from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/bartender-opacified.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/red_cream_ud_logo_transparent.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            logo: logo,
            bartenderImg: bartenderImg
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
    position: relative; left: 50;
}

.container {
    background-color: white;
    align-items: center;
    justify-content: center;
    flex: 1;
}

.logo {
    height: 103%;
    width: 103%;
    position: relative; bottom: 50; right: 50;
    opacity: 1;
}

.button-container {
    display: flex;
    flex-direction: row;
    position: relative; bottom: 87; right: 52;
}

.button-1 {
    background-color: #8D1B33;
    width: 190;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
}

.button-2 {
    background-color: #8D1B33;
    width: 190;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
}

.button-text {
    color: #F7C7AA;
    font-size: 40;
    font-family: Helvetica;
}
</style>
