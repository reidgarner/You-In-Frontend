<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="username-container">
                <text-input class="input" auto-capitalize="none" v-model="workplace" placeholder="Search for Workplace"/>
                <image class="map"
                :style="{width: 300, height: 300, borderRadius: 20}"
                :source="map"
                />
            </view>
            <image :source="logo" class="logo"></image>
            <touchable-opacity class="button" :on-press="handleUser">
                <text class="button-text">Add Workplace</text>
            </touchable-opacity>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
import logo from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_transparent.png";
import map from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/Map.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            workplace: '',
            bartenders: [
                { name: "Reid Garner", workplace: "Five Bar"}
            ],
            beerBackdrop: beerBackdrop,
            logo: logo,
            map: map
        }
    },

    methods: {
        handleUser() {
            this.navigation.navigate("User");
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

.add-workplace {
    font-size: 50;
    color: whitesmoke;
}

.workplace {
    font-size: 40;
    color: whitesmoke;
}

.input {
    height: 50; 
    width: 300; 
    border-radius: 10; 
    border-color: gray; 
    border-width: 1;
    background-color: whitesmoke;
}

.username-container {
    align-items: center;
    position: relative; top: 140;
}

.map {
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
    width: 300;
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
    font-size: 40;
    font-family: Helvetica;
}
</style>