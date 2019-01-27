<template>
    <view class="container">
        <image-background :source="bartenderImg" class="imageContainer">
            <image :source="logo" class="logo"></image>
            <image :source="logo2" class="logo2"></image>
            <view class="button-container">
                <touchable-opacity class="button-1" :on-press="handleGuestLogin">
                    <text class="button-text">Bar Guest</text>
                </touchable-opacity>
                <touchable-opacity class="button-2" :on-press="handleBTLogin">
                    <text class="button-text">Bartender</text>
                </touchable-opacity>
            </view>
        </image-background>
    </view>
</template>

<script>
import bartenderImg from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/Bartender3-Background.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/red_cream_ud_logo_transparent.png";
import logo2 from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/YouIn_transparent.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            logo: logo,
            logo2: logo2,
            bartenderImg: bartenderImg
        }
    },

    methods: {
        handleGuestLogin() {
            this.navigation.navigate("GuestSU");
        },
        handleBTLogin() {
            this.navigation.navigate("BTSignUp");
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

.imageContainer {
    flex: 1;
    align-items: center;
    justify-content: center;
    width: 130%;
    position: relative; left: 46;
}

.logo {
    height: 103%;
    width: 103%;
    position: relative; top: 332; right: 45;
    opacity: .78;
}

.logo2 {
    height: 110%;
    width: 105%;
    position: relative; bottom: 372; right: 45;
    opacity: 1;
}

.button-container {
    width: 73%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    position: relative; bottom: 495; right: 46.5;
}

.button-1 {
    background-color: #8D1B33;
    width: 170;
    height: 60;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    opacity: .85;
}

.button-2 {
    background-color: #8D1B33;
    width: 170;
    height: 60;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    opacity: .85;
}

.button-text {
    color: #F7C7AA;
    font-size: 30;
    font-family: Helvetica;
}
</style>