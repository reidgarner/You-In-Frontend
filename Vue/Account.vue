<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <text class="title">Account</text>
            <image :source="logo" class="logo"></image>
            <view class="button-container">
                <touchable-opacity class="button" :on-press="handleEditInfo">
                    <text class="button-text">Edit Info</text>
                </touchable-opacity>
                <touchable-opacity class="button" :on-press="handleAddWork">
                    <text class="button-text">Add Workplace</text>
                </touchable-opacity>
                <touchable-opacity class="button" :on-press="handleDelete">
                    <text class="button-text">Delete Account</text>
                </touchable-opacity>
            </view>
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
            beerBackdrop: beerBackdrop,
            logo: logo
        }
    },

    methods: {
        handleEditInfo() {
            this.navigation.navigate("EditInfo");
        },
        handleAddWork() {
            this.navigation.navigate("PlaceOfWork");
        },
        handleDelete() {
            this.navigation.navigate("Main");
        },
        
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

.title {
    color: #F7C7AA;
    font-size: 50;
    font-family: Helvetica;
    position: relative; top: 50;
}

.button-container {
    height: 200;
    width: 300; 
    display: flex;
    justify-content: space-around;
    position: relative; bottom: 150;
}

.button {
    background-color: #8D1B33;
    width: 300;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-text {
    color: #F7C7AA;
    font-size: 40;
    font-family: Helvetica;
}

.logo {
    height: 70%;
    width: 70%;
    position: relative; top: 25;
    opacity: .78;
}
</style>