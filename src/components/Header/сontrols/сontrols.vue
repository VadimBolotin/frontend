<script setup lang="ts">
    import { AkIcon, Basket, Like } from '@/assets';
    import styles from './styles.module.scss'
</script>

<template>
    <div :class="styles.controls">
        <div :class="styles.favorite">
            <Like/>
        </div>

        <div :class="styles.box">
            <div :class="styles.cart">Cart</div>
            <div :class="styles.cartIcon">
                <div :class="styles.cartIconBord">
                    <Basket/>
                </div>
            </div>
        </div>

        <div :class="styles.account">
            <AkIcon/>
        </div>
    </div>
</template>