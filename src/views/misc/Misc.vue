<template>
    <div class="x--list">
        <h3>Misc 其他</h3>
        <p>
            <router-link :to="{ name: 'misc.request'}">Mock</router-link>
        </p>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'Misc'
})
</script>
