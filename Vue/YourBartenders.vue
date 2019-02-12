<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="your-bartenders-container">
                <image :source="YourBartender1" class="YourBartender1"></image>
                <image :source="YourBartender2" class="YourBartender2"></image>
            </view>
            <scroll-view :style="{width: '100%'}">
                <view class="bartender-list" v-for="(bartender, index) in bartenders" :key="index">
                    <touchable-opacity class="flex-container" :on-press="() => handleListTap(bartender)">
                        <image 
                        :style="{width: 50, height: 50, borderRadius: 25, marginRight: 8}"
                        :source="{uri: bartender.image}"
                        />
                        <text class="bartender-name"> {{ bartender.name }}</text>
                        <text class="IO">{{ bartender.IO }}</text>
                    </touchable-opacity>
                </view>
            </scroll-view>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
import YourBartender1 from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/YourBartenders_Black.png";
import YourBartender2 from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/YourBartenders_Tan.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            bartenders: [
                { name: "Andrew Pedersen", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQEpxR0WN9GdcQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=oiOQvx3RNjfSSIDt8WZPY2KxHzdU5mZt77ru6btBE0o"},
                { name: "Dane Parke", IO: "IN", image: "https://scontent-sjc3-1.xx.fbcdn.net/v/t1.0-9/38071940_10217130278918784_8573175157164605440_o.jpg?_nc_cat=110&_nc_ht=scontent-sjc3-1.xx&oh=f8ff3ce9c82a9098da7b40dd94acf6e5&oe=5CC02997"},
                { name: "Evan Young", IO: "IN", image: "https://scontent-sjc3-1.xx.fbcdn.net/v/t1.0-9/20992580_10214007762654107_3573172220081135910_n.jpg?_nc_cat=101&_nc_ht=scontent-sjc3-1.xx&oh=e476b5f1ea3d5fb0835033d33475fb69&oe=5CFE24A2"}
            ],
            beerBackdrop: beerBackdrop,
            YourBartender1: YourBartender1,
            YourBartender2: YourBartender2
    }
    },

    methods: {
        handleButton() {
            this.navigation.navigate("Login");
        },
        handleListTap(bartender) {
            console.log(bartender.name) 
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

.your-bartenders-container {
    height: 80;
    width: 300;
    display: flex;
    justify-content: center;
    align-items: center;
}

.YourBartender1 {
    height: 143%;
    width: 143%;
    position: relative; top: 85;
}

.YourBartender2 {
    height: 148%;
    width: 145%;
    position: relative; bottom: 30;
}

.bartender-list {
    padding: 15;
    position: relative; bottom: 5;
}

.flex-container {
    flex-direction: row;
    align-items: center;
}

.bartender-name {
    color: whitesmoke;
    font-size: 27;
}

.IO {
    color: whitesmoke;
    margin-left: auto;
    font-size: 30;
}
</style>