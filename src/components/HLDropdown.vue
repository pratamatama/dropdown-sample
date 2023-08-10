<template>
  <div class="w-full">
    <label class="font-medium text-xs">Pilih Anggota Klub</label>
    <Listbox v-model="selectedPerson" class="w-full text-black dark:text-white">
      <div class="relative mt-1">
        <ListboxButton
          class="relative w-full cursor-default rounded-lg bg-white dark:bg-gray-800 py-2 pl-3 pr-10 text-left shadow-md focus:outline-none focus-visible:border-indigo-500 focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75 focus-visible:ring-offset-2 focus-visible:ring-offset-orange-300 sm:text-sm"
        >
          <span class="block truncate">{{ selectedPerson.name }}</span>
          <span
            class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-2"
          >
            <ChevronUpDownIcon
              class="h-5 w-5 text-gray-400"
              aria-hidden="true"
            />
          </span>
        </ListboxButton>

        <transition
          leave-active-class="transition duration-100 ease-in"
          leave-from-class="opacity-100"
          leave-to-class="opacity-0"
        >
          <ListboxOptions
            class="absolute z-10 mt-1 max-h-60 w-full overflow-auto rounded-md bg-white dark:bg-gray-800 py-1 text-base shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none sm:text-sm"
          >
            <ListboxOption
              v-slot="{ active, selected }"
              v-for="person in people"
              :key="person.name"
              :value="person"
              as="template"
            >
              <li
                :class="[
                  active
                    ? 'bg-amber-100 dark:bg-amber-500/5 text-amber-900 dark:text-amber-400'
                    : 'text-gray-900 dark:text-white',
                  'relative cursor-default select-none py-2 pl-10 pr-4',
                ]"
              >
                <span
                  :class="[
                    selected ? 'font-medium' : 'font-normal',
                    'block truncate',
                  ]"
                  >{{ person.name }}</span
                >
                <span
                  v-if="selected"
                  class="absolute inset-y-0 left-0 flex items-center pl-3 text-green-600 dark:text-green-400"
                >
                  <CheckIcon class="h-5 w-5" aria-hidden="true" />
                </span>
              </li>
            </ListboxOption>
          </ListboxOptions>
        </transition>
      </div>
    </Listbox>
    <p class="mt-1 text-gray-500 text-xs">
      Lorem ipsum dolor sit amet consectetur adipisicing elit.
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";
import {
  Listbox,
  ListboxLabel,
  ListboxButton,
  ListboxOptions,
  ListboxOption,
} from "@headlessui/vue";
import { CheckIcon, ChevronUpDownIcon } from "@heroicons/vue/20/solid";

const people = [
  { name: "Wade Cooper" },
  { name: "Arlene Mccoy" },
  { name: "Devon Webb" },
  { name: "Tom Cook" },
  { name: "Tanya Fox" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
  { name: "Hellen Schmidt" },
];
const selectedPerson = ref(people[0]);
</script>
