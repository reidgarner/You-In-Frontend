<template>
    <view class="container">
        <text class="title">Account</text>
        <touchable-opacity class="button-1" :on-press="handleEdit">
            <text class="button-text">Edit Info</text>
        </touchable-opacity>
        <touchable-opacity class="button-2" :on-press="handleAddWork">
            <text class="button-text">Add Workplace</text>
        </touchable-opacity>
        <touchable-opacity class="button-3" :on-press="handleDelete">
            <text class="button-text">Delete Account</text>
        </touchable-opacity>
    </view>
</template>

<script>
import { Font } from 'expo';

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    async mounted() {
        await Expo.Font.loadAsync({
            'Reenie Beanie': require('./assets/fonts/ReenieBeanie.ttf')
        })
    this.isLoaded = true;
    },

    methods: {
        handleEdit() {
            this.navigation.navigate("EditInfo");
        },
        handleAddWork() {
            this.navigation.navigate("AddWork");
        },
        handleDelete() {
            this.navigation.navigate("Main");
        },
        
    }
}
</script>

<style>
.container {
    background-color: white;
    align-items: center;
    flex: 1;
}

.title {
    font-size: 50;
    /* position: relative; bottom: 375; */
    font-family: Courier;
}

.username {
    font-size: 30;
}

.workplace {
    font-size: 20;
}

.username-container {
    align-items: center;
}

.button-1 {
    background-color: rgb(67, 67, 67);
    width: 380;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-2 {
    background-color: rgb(67, 67, 67);
    width: 380;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 80;
}

.button-3 {
    background-color: rgb(67, 67, 67);
    width: 380;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 110;
}

.button-text {
    color: rgb(159, 159, 159);
    font-size: 40;
    font-family: Courier;
}

</style>