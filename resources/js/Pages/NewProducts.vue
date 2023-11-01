<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import ClearSVG from '@/Components/IconsSVG/ClearSVG.vue';
import draggable from 'vuedraggable';
import { ref } from 'vue';

const meals = ref([]);

const handleFileUpload = (event) => {
  const files = event.target.files;
  for (let i = 0; i < files.length; i++) {
    const file = files[i];
    const imageUrl = URL.createObjectURL(file);
    meals.value.push(imageUrl);
  }
};

const removeImage = (index) => {
  meals.value.splice(index, 1);
};
</script>

<template>
  <AppLayout title="Products">
    <div class="px-4">
      <div class="max-w-8xl mx-auto sm:px-6 lg:px-8">
        <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
          <section class="bg-gray-100">
            <div class="mx-auto max-w-screen-xl px-4 py-16 sm:px-6 lg:px-8">

              <div class="flex gap-8">

                <div class="rounded-lg bg-white p-8 shadow-lg lg:col-span-3 lg:p-12 w-3/6">
                  <form action="" class="space-y-4">
                    <div>
                      <label class="sr-only" for="name">Name</label>
                      <input class="w-full rounded-lg border-gray-200 p-3 text-sm" placeholder="Name" type="text"
                        id="name" />
                    </div>

                    <div>
                      <label class="sr-only" for="price">Price</label>
                      <input class="w-full rounded-lg border-gray-200 p-3 text-sm" placeholder="Price" type="number"
                        id="price" />
                    </div>


                    <div>
                      <label class="sr-only" for="description">Description</label>

                      <textarea class="w-full rounded-lg border-gray-200 p-3 text-sm" placeholder="Description" rows="8"
                        id="description"></textarea>
                    </div>

                    <div class="mt-4">
                      <button type="submit"
                        class="inline-block w-full rounded-lg bg-black px-5 py-3 font-medium text-white sm:w-auto">
                        Create product
                      </button>
                    </div>
                  </form>
                </div>

                <div class="rounded-lg bg-white p-8 shadow-lg lg:col-span-3 lg:p-12 w-3/6 flex flex-col justify-between">
                  <div class="bg-gray-100 w-full h-[70%] rounded-2xl">
                    <draggable v-model="meals" tag="div" class="flex gap-5 flex-wrap p-8">
                      <template #item="{ element: meal, index }">
                        <div class="p-2 rounded-lg bg-gray-100 relative">
                          <div
                            class="absolute flex justify-center items-center rounded-full border-solid border border-black border-1 p-1 bottom-[90px] left-[-5px] bg-white w-7 h-7 text-xs">
                            <span>{{ index + 1 }}</span>
                          </div>
                          <div @click="removeImage(index)"
                            class="absolute flex justify-center items-center rounded-full border-solid border border-black border-1 p-1 bottom-[90px] left-[81%] bg-white w-7 h-7 text-xs font-bold transition hover:text-red-600 cursor-pointer">
                            <ClearSVG />
                          </div>
                          <img :src="meal" class="rounded-lg object-cover w-[103px] h-[90px]" />
                        </div>
                      </template>
                    </draggable>
                  </div>
                  <div class="bg-grey-lighter mt-4">
                    <label
                      class="w-64 h-12 flex flex-row justify-center items-center px-4 py-6 rounded-lg tracking-wide border  cursor-pointer hover:shadow-lg">
                      <font-awesome-icon icon="upload" class="p-2" />
                      <span class="mt-2 text-base leading-normal">Select a file</span>
                      <input type='file' class="hidden" @change="handleFileUpload" multiple />
                    </label>
                  </div>
                </div>

              </div>
            </div>
          </section>
        </div>
      </div>
    </div>
  </AppLayout></template>
