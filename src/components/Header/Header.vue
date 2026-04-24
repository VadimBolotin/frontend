<script setup lang="ts">
    import { Logo } from '@/assets';   
    import Burger from './burger/burger.vue';
    import Controls from './сontrols/сontrols.vue'
    import styles from './styles.module.scss'
</script>

<template>
    <div
        :class="styles.header"
    >
        <div
            :class="styles.inner"
        >
            <Burger/>
            <Logo/>
            <Controls/>
        </div>
    </div>
</template>