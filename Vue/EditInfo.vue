<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="logo-container">
                <image :source="logo" class="logo"></image>
                <image :source="logo2" class="logo2"></image>
            </view>
            <view class="input-container">
                <text-input class="input" auto-capitalize="none" v-model="first_name" placeholder="First Name"/>
                <text-input class="input" auto-capitalize="none" v-model="last_name" placeholder="Last Name"/>
                <text-input class="input" auto-capitalize="none" v-model="email" placeholder="Email"/>
                <text-input class="input" auto-capitalize="none" v-model="password" placeholder="Password"/>
            </view>
            <touchable-opacity class="button" :on-press="handleAccount">
                <text class="button-text">Edit Info</text>
            </touchable-opacity>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
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
            first_name: '',
            last_name: '',
            email: '',
            password: '',
            logo: logo,
            logo2: logo2,
            beerBackdrop: beerBackdrop
    }
    },

    methods: {
        handleAccount() {
            this.navigation.navigate("Account");
        }
    }
}
</script>

<style>
.container {
    background-color: rgb(99, 99, 99);
    align-items: center;
    justify-content: center;
    flex: 1;
}

.imageContainer {
    flex: 1;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.logo-container {
    height: 300;
    width: 200;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative; top: 0;
}

.logo {
    height: 120%;
    width: 120%;
    position: relative; top: 163;
    opacity: .78;
}

.logo2 {
    height: 124%;
    width: 120%;
    position: relative; bottom: 171;
    opacity: 1;
}

.button {
    background-color: #8D1B33;
    width: 170;
    height: 60;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    opacity: .85;
    position: relative; bottom: 40;
}

.button-text {
    color: #F7C7AA;
    font-size: 30;
    font-family: Helvetica;
}

.input-container {
    display: flex;
    justify-content: space-evenly;
    height: 250;
    width: 300;
    position: relative; bottom: 50;
    opacity: .85;
}

.input {
    height: 50; 
    width: 300; 
    border-radius: 10; 
    border-color: gray; 
    border-width: 1;
    background-color: whitesmoke;
}
</style>