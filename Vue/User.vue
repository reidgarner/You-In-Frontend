<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="username-container" v-for="(bartender, index) in bartenders" :key="index">
                <text class="username" >{{ bartender.name }}</text>
                <text class="workplace" >@{{ bartender.workplace }}</text>
                <image class="QRcode"
                :style="{width: 300, height: 300, borderRadius: 20}"
                :source="QRCode"
                />
            </view>
            <image :source="logo" class="logo"></image>
            <touchable-opacity class="button" :on-press="handleYourGuests">
                <text class="button-text">Your Guests</text>
            </touchable-opacity>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_transparent.png";
import QRCode from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/QR_Code.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            bartenders: [
                { name: "Reid Garner", workplace: "Five Bar"}
            ],
            beerBackdrop: beerBackdrop,
            logo: logo,
            QRCode: QRCode
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
    background-color: rgb(99, 99, 99);
    align-items: center;
    flex: 1;
}

.imageContainer {
    flex: 1;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.username {
    font-size: 60;
    color: whitesmoke;
}

.workplace {
    font-size: 40;
    color: whitesmoke;
}

.username-container {
    align-items: center;
    position: relative; top: 140;
}

.QRcode {
    position: relative; top: 15;
}

.logo {
    height: 70%;
    width: 70%;
    position: relative; top: 47;
    opacity: .78;
}

.button {
    background-color: #8D1B33;
    width: 250;
    height: 60;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    opacity: .85;
    position: relative; bottom: 180;
}
.button-text {
    color: #F7C7AA;
    font-size: 30;
    font-family: Helvetica;
}
</style>