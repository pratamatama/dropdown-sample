<script setup>
import { ref } from "vue";
import { CheckIcon, ChevronUpDownIcon } from "@heroicons/vue/20/solid";
import { onClickOutside } from "@vueuse/core";

const isOpen = ref(false);

const target = ref(null);
onClickOutside(target, () => (isOpen.value = false));

const persons = [
  { name: "Wade Cooper" },
  { name: "Arlene Mccoy" },
  { name: "Devon Webb" },
  { name: "Tom Cook" },
  { name: "Tanya Fox" },
  { name: "Hellen Schmidt" },
];

const selectedPerson = ref(persons[0]);

const select = (person) => {
  selectedPerson.value = person;
  isOpen.value = false;
};
</script>

<template>
  <div>
    <label class="font-medium text-xs block mb-2">Pilih Anggota Klub</label>
    <div class="relative">
      <button
        ref="target"
        @click.prevent="isOpen = !isOpen"
        class="w-full bg-gray-800 rounded-lg p-2 pl-4 pr-2 text-left"
      >
        <div class="flex justify-between items-center">
          <span>{{ selectedPerson.name }}</span>
          <ChevronUpDownIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />
        </div>
      </button>

      <ul
        v-if="isOpen"
        class="absolute z-10 inset-x-0 bg-gray-800 w-full mt-1 rounded-lg py-1 max-h-72 overflow-y-auto"
      >
        <li
          v-for="person in persons"
          :key="person.name"
          class="py-2 hover:bg-amber-400/5 hover:text-amber-400 p-4"
          :class="{
            'bg-amber-400/5 text-amber-400 font-medium':
              selectedPerson.name === person.name,
          }"
          @click="select(person)"
        >
          <div class="flex items-center">
            <CheckIcon
              v-if="selectedPerson.name === person.name"
              class="h-5 w-5 text-green-400"
              aria-hidden="true"
            />
            <div v-else class="h-5 w-5" />
            <span class="ml-2">{{ person.name }}</span>
          </div>
        </li>
      </ul>
    </div>
    <p class="mt-1 text-gray-500 text-xs">
      Lorem ipsum dolor sit amet consectetur adipisicing elit.
    </p>
  </div>
</template>
