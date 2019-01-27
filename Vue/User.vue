<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="username-container" v-for="(bartender, index) in bartenders" :key="index">
                <text class="username" >{{ bartender.name }}</text>
                <text class="workplace" >{{ bartender.workplace }}</text>
                <image class="QRcode"
                :style="{width: 300, height: 300, borderRadius: 20}"
                :source="{uri: bartender.qr}"
                />
            </view>
            <image :source="logo" class="logo"></image>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_transparent.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            bartenders: [
                { name: "Reid Garner", workplace: "@Five Bar", qr: "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/QR_Code.png"}
            ],
            beerBackdrop: beerBackdrop,
            logo: logo
        }
    },
}
</script>

<style>
.container {
    background-color: black;
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
    position: relative; top: 115;
}

.QRcode {
    position: relative; top: 50;
}

.logo {
    height: 70%;
    width: 70%;
    position: relative; top: 100;
    opacity: .78;
}
</style>