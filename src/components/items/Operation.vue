<template>
    <div class="operation">
        <ul class="operations">
            <li v-for="(item,index) in operations">
                <span :class="[item.danger ? redHand: blueHand, hand]"></span>
                <span>{{new Date(item.recent).toLocaleString()}}</span><span><strong>{{item.controller}}</strong></span><span>{{item.operate}}</span><span>{{item.target}}</span>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    props: {
        operations: {
            type: Array,
            default: () => {
                return [];
            }
        }
    },
    data() {
        return {
            redHand: 'redHand',
            blueHand: 'blueHand',
            hand: 'hand'
        }
    },
    // beforeCreate() {
    //     console.log('Operation.vue beforeCreate');
    // },
    // created() {
    //     console.log('Operation.vue Created');
    // },
    // beforeMount() {
    //     console.log('Operation.vue beforeMount');
    // },
    mounted() {
        console.log('Operation.vue mounted');
        new Date().toLocaleString()
    },
    // beforeUpdate() {
    //     console.log('Operation.vue beforeUpdate');
    // },
    updated() {
        console.log('Operation.vue updated');
        // console.log('Operation.vue dynamics', this.$store.state.dynamicData);
    },
    // beforeDestroy() {
    //     console.log('Operation.vue beforeDestroy');
    // },
    destroyed() {
        console.log('Operation.vue destroyed');
    },
}
</script>
<style scoped>
.operation{
    padding-top: 4px;
}
.operations li{
    font-size: 14px;
    height: 20px;
    line-height: 20px;
    vertical-align: middle;
    white-space: nowrap;
    text-overflow: ellipsis;
    overflow: hidden;
    margin-top: 4px;
}
.operations span{
    margin-right: 4px;
}
</style>