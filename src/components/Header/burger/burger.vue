<script setup lang="ts">
    import { Burger } from '@/assets';
    import styles from './styles.module.scss'
    import { ref } from 'vue';

    interface MenuItem {
        id: number, 
        title: string
    }

    const burgerItems: MenuItem[] = [
        {id: 1, title: 'Home'},
        {id: 2, title: 'Collections'},
        {id: 3, title: 'New'},
    ]

    const activeId = ref(1)

    const handleItemClick = (item: MenuItem) => {
        console.log('Clicked:', item.title)
        activeId.value = item.id
    }

</script>

<template>
    <div :class="styles.burger">
        <Burger/>

        <ul :class="styles.items">
            <li
                v-for="item in burgerItems" 
                :key="item.id"
                :class="[
                    styles.item,
                    { [styles.active]: activeId === item.id }
                ]"
                @click="handleItemClick(item)"
            >
                {{ item.title }}
            </li>
        </ul>
    </div>
</template>