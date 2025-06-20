<script setup>
import { Button } from '@/components/ui/button'
import { Avatar, AvatarImage, AvatarFallback } from '@/components/ui/avatar'

import { Icon } from '@iconify/vue'
import { useColorMode } from '@vueuse/core'
import { DropdownMenu, DropdownMenuContent, DropdownMenuItem, DropdownMenuTrigger } from '@/components/ui/dropdown-menu'

const mode = useColorMode()
</script>

<template>
  <nav class="flex justify-between items-center p-4">
    <h1 class="text-2xl font-bold text-violet-500">CatPanel </h1>
    <div class="flex items-center gap-4">
      <!-- <Button variant="outline" class="bg-blue-500 text-white cursor-pointer">Login</Button> -->

      <!-- Dark Mode Toggle -->
      <DropdownMenu>
        <DropdownMenuTrigger as-child>
          <Button variant="outline" class="cursor-pointer">
            <Icon icon="radix-icons:moon"
              class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
            <Icon icon="radix-icons:sun"
              class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
            <span class="sr-only">Toggle theme</span>
          </Button>
        </DropdownMenuTrigger>
        <DropdownMenuContent align="end">
          <DropdownMenuItem @click="mode = 'light'" class="cursor-pointer">
            Light
          </DropdownMenuItem>
          <DropdownMenuItem @click="mode = 'dark'" class="cursor-pointer">
            Dark
          </DropdownMenuItem>
          <DropdownMenuItem @click="mode = 'auto'" class="cursor-pointer">
            System
          </DropdownMenuItem>
        </DropdownMenuContent>
      </DropdownMenu>
      <Avatar class=" cursor-pointer">
        <AvatarImage src="https://github.com/shadcn.png" />
        <AvatarFallback>CN</AvatarFallback>
      </Avatar>
    </div>
  </nav>
</template>