<template>
    <Link 
        class="w-full flex items-center rounded-md px-2 py-1"
        :class='{ "bg-gray-500 text-white": active, "font-bold underline": compActive }' 
    >
        <slot />
    </Link>
</template>

<script setup>
  //import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue'
  //import { PencilIcon, DocumentDuplicateIcon, XCircleIcon, AdjustmentsHorizontalIcon, Bars3Icon } from '@heroicons/vue/24/outline'

  defineProps({
    compActive : Boolean, 
    active : Boolean,
    //component: String, 
  })
</script>