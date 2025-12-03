<script>
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
<!-- From Uiverse.io by SmookyDev --> 
    <label class="relative inline-flex items-center cursor-pointer">
    <input class="sr-only peer" value="" type="checkbox" @change="toggleDark()" :checked="isDark"  />
    <div
        class="w-12 h-5.5 rounded-full ring-0 peer duration-500 outline-none bg-gray-200 overflow-hidden before:flex before:items-center before:justify-center after:flex after:items-center after:justify-center before:content-['☀️'] before:absolute before:h-5 before:w-5 before:top-1/2  before:rounded-full before:left-1 before:-translate-y-1/2 before:transition-all before:duration-700 peer-checked:before:opacity-0 peer-checked:before:rotate-90 peer-checked:before:-translate-y-full shadow-lg after:content-['🌑'] after:absolute after:bg-[#1d1d1d] after:rounded-full after:top-[1px] after:right-1 after:translate-y-full after:w-5 after:h-5 after:opacity-0 after:transition-all after:duration-700 peer-checked:after:opacity-100 peer-checked:after:rotate-180 peer-checked:after:translate-y-0"
    ></div>
    </label>


</template>