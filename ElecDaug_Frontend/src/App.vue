<template>
    <div id="app" style="width: 100vw; height: 100vh">
        <router-view v-if="isRouterAlive"></router-view>
    </div>
</template>
<script>
export default {
    name: 'App',
    provide() {
        return {
            reload: this.reload
        };
    },
    data() {
        return {
            isRouterAlive: true
        };
    },
    methods: {
        reload() {
            this.isRouterAlive = false;
            this.$nextTick(function() {
                this.isRouterAlive = true;
            });
        }
    }
};
</script>
<style>
@import './assets/css/main.css';
@import './assets/css/color-dark.css';
</style>
