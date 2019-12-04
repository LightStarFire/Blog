<template>
    <div class="page-index clearFix">
        <template v-for="(yItem, yIndex) in canSeeHeight">
            <template v-for="(xItem, xIndex) in canSeeWidth">
                <div  :key="xIndex + '-' + yIndex" :style="assignedBackgroundImage(xIndex, yIndex)" class="fl"></div>
            </template>
        </template>
    </div>
</template>

<script>
export default {
    name: 'index',
    data () {
        return {
            canSeeHeight: 0,
            canSeeWidth: 0
        }
    },
    mounted () {
        this.canSeeHeight = document.body.clientHeight / 10;
        this.canSeeWidth = document.body.clientWidth / 10;
    },
    methods: {
        assignedBackgroundImage (xLocation, yLocation) {
            return 'background: url("../../../static/images/bzh.jpg") no-repeat ' + (xLocation * -10 + 'px ') + (yLocation * -10 + 'px')
        }
    }
}
</script>

<style scoped>
.page-index {
    width: 100vw;
    height: 100vh;
    /* background-image: url('../../../static/images/bzh.jpg'); */
}
.page-index .fl {
    width: 10px;
    height: 10px;
}
</style>
