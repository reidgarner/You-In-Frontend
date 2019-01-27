<template>
    <view class="container">
        <image-background :source="bartenderImg" class="imageContainer">
            <image :source="logo" class="logo"></image>
            <image :source="logo2" class="logo2"></image>
            <text class="As-a">Bartender</text>
            <view class="input-container">
                <text-input class="input" auto-capitalize="none" v-model="first_name" placeholder="First Name"/>
                <text-input class="input" auto-capitalize="none" v-model="last_name" placeholder="Last Name"/>
                <text-input class="input" auto-capitalize="none" v-model="email" placeholder="Email"/>
                <text-input class="input" auto-capitalize="none" v-model="password" placeholder="Password"/>
            </view>
            <touchable-opacity class="button" :on-press="handleYourGuests">
                <text class="button-text">Signup</text>
            </touchable-opacity>
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
            first_name: '',
            last_name: '',
            email: '',
            password: '',
            logo: logo,
            logo2: logo2,
            bartenderImg: bartenderImg
        }
    },

    methods: {
        handleYourGuests() {
            this.navigation.navigate("YourGuests");
        }
    }
}
</script>

<style>
.container {
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
    height: 50%;
    width: 50%;
    position: relative; top: 175; right: 45;
    opacity: .78;
}

.logo2 {
    height: 54%;
    width: 50%;
    position: relative; bottom: 169; right: 45;
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
    position: relative; bottom: 235; right: 47;
}

.button-text {
    color: #F7C7AA;
    font-size: 30;
    font-family: Helvetica;
}

.As-a {
    color: black;
    font-size: 40;
    font-family: Helvetica;
    position: relative; bottom: 250; right: 47;
}

.input-container {
    display: flex;
    justify-content: space-evenly;
    height: 250;
    width: 300;
    position: relative; bottom: 250; right: 47;
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