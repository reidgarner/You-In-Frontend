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
export default {
    props: {
        navigation: {
            type: Object
        }
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
    font-family: Helvetica;
}

.button-1 {
    background-color: rgb(67, 67, 67);
    width: 300;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-2 {
    background-color: rgb(67, 67, 67);
    width: 300;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 80;
}

.button-3 {
    background-color: rgb(67, 67, 67);
    width: 300;
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
    font-family: Helvetica;
}
</style>