<script setup>
import Dropdown from "@/components/Dropdown.vue";
import HLDropdown from "@/components/HLDropdown.vue";
</script>

<template>
  <main
    class="h-screen bg-gray-900 text-white flex flex-col justify-center items-center"
  >
    <div class="w-[400px] h-full flex flex-col justify-center items-start">
      <div class="w-full space-y-4">
        <Dropdown />
        <HLDropdown />
      </div>
    </div>
  </main>
</template>
