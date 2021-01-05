<template>
    <view>
        <view>
            <text>Hello {{ name }}</text>
            <text class="red">
                {{ ios ? 'ios' : 'android' }}
            </text>
        </view>
        <touchable-opacity :on-press="onPress">
            <text>点击</text>
        </touchable-opacity>

        <view class="back" />
    </view>
</template>
<style>
.red {
    color: red;
}
.back {
    width: 30;
    height: 30;
    border-top-width: 4;
    border-left-width: 4;
    border-top-color: #ff6600;
    border-left-color: #ff6600;
    margin-left: 8;
    align-self: center;
    transform: rotate(-45deg) scale(0.5);
}
</style>

<script>
import { Platform } from 'react-native'
export default {
    props: {
        defaultIndex: {
            type: Number,
            default: 0
        }
    },
    data() {
        return {
            name: 'react-vue'
        }
    },
    computed: {
        ios() {
            return Platform.OS === 'ios'
        },
        android() {
            return Platform.OS === 'android'
        }
    },
    methods: {
        onPress() {
            alert('ok')
        }
    },
    mounted() {}
}
</script>
