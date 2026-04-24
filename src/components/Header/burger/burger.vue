<script setup lang="ts">
    import { Burger } from '@/assets';
    import styles from './styles.module.scss'
    import { onMounted, onUnmounted, ref } from 'vue';

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
    const isMenuOpen = ref(false)
    const isMobile = ref(false)


    const checkMobile = () => {
        isMobile.value = window.innerWidth <= 1024 
    }

    const handleItemClick = (item: MenuItem) => {
        console.log('Clicked:', item.title)
        activeId.value = item.id
        isMenuOpen.value = false
    }

    const toggleMenu = () => {
        if (isMobile.value) {
            isMenuOpen.value = !isMenuOpen.value
        }
    }

    const closeMenu = () => {
        isMenuOpen.value = false
    }

    onMounted(() => {
        checkMobile()
        window.addEventListener('resize', checkMobile)
    })

    onUnmounted(() => {
        window.removeEventListener('resize', checkMobile)
    })

</script>

<template>
    <div :class="styles.burger">
        <div @click="toggleMenu">
            <Burger/>
        </div>
        

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

        <Transition name="mobile-menu">
            <div v-if="isMenuOpen" :class="styles.mobileMenu">
                <div :class="styles.closeButton" @click="closeMenu">
                    <span></span>
                    <span></span>
                </div>
                <ul :class="styles.mobileItems">
                    <li
                        v-for="item in burgerItems" 
                        :key="item.id"
                        :class="[
                            styles.mobileItem,
                            { [styles.active]: activeId === item.id }
                        ]"
                        @click="handleItemClick(item)"
                    >
                        {{ item.title }}
                    </li>
                </ul>
            </div>
        </Transition>
    </div>
</template>