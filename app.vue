<script setup lang="ts">
import { Button } from '@/components/ui/button'
import { DropdownMenu, DropdownMenuContent, DropdownMenuItem, DropdownMenuTrigger } from '@/components/ui/dropdown-menu'

const colorMode = useColorMode()
</script>

<template>
  <div class="min-h-screen bg-background text-foreground transition-colors">
    <!-- Navbar -->
    <header class="flex items-center justify-between px-6 py-4 border-b">
      <h1 class="text-lg font-semibold">My App</h1>
      <DropdownMenu>
            <DropdownMenuTrigger as-child>
              <Button variant="outline">
                <Icon name="mdi-light:lightbulb-on" class="h-[2.2rem] w-[2.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
                <Icon name="mdi-light:lightbulb" class="absolute h-[2.2rem] w-[2.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
                <span class="sr-only">Toggle theme</span>
              </Button>
            </DropdownMenuTrigger>
            <DropdownMenuContent align="end">
              <DropdownMenuItem @click="colorMode.preference = 'light'">
                Light
              </DropdownMenuItem>
              <DropdownMenuItem @click="colorMode.preference = 'dark'">
                Dark
              </DropdownMenuItem>
              <DropdownMenuItem @click="colorMode.preference = 'system'">
                System
              </DropdownMenuItem>
            </DropdownMenuContent>
          </DropdownMenu>
    </header>

    <!-- Page content injected here -->
    <NuxtPage />

    <!-- Optional footer -->
    <footer class="mt-12 py-6 text-center text-sm text-muted-foreground border-t">
      © {{ new Date().getFullYear() }} My App. All rights reserved.
    </footer>
  </div>
</template>