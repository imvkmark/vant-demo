<template>
    <div class="height">
        <pre># app {
    height:100%;
    height:100vh; ios: 15.0
}
        </pre>
        <pre># height {height: 100%;}</pre>
        <code>
            os :
            <br>
            {{ ua.getOS() }} <br>
            browser :
            <br>
            {{ ua.getBrowser() }} <br>
            ua :
            <br>
            {{ ua.getUA() }} <br>
            dpr : {{ dpr }}
        </code>
        <div v-for="x in 100" :key="x">
            <p>
                Axios Request Page {{ x }} / 100
            </p>
        </div>
    </div>
</template>

<script lang="ts" setup>
import UAParser from "ua-parser-js";
import { onMounted } from "vue";

let ua = new UAParser(navigator.userAgent)

const dpr = window.devicePixelRatio;

onMounted(() => {
    if (ua.getOS().name === 'iOS' && ua.getOS().version === '15.0') {
        if (document.documentElement.hasAttribute('fix-height')) {
            document.documentElement.removeAttribute('fix-height');
        }
        document.documentElement.setAttribute('fix-height', 'vh');
    }
})
</script>

<style lang="less">
#app {
    border: 8px solid var(--wr-border-color);
}
</style>
<style lang="less" scoped>
.height {
    border: 1px solid var(--wr-title-color);
    box-sizing: border-box;
    height: 100%;
    overflow-y: auto;
}
</style>
