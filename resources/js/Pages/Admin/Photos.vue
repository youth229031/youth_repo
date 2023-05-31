
<template>
  <app-layout title="Dashboard">
      <template #header>
          <h2 class="font-semibold text-xl text-gray-800 leading-tight">Photos</h2>
      </template>

       <div class="py-12">
          <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
            <!-- All posts goes here -->
            <h1 class="text-2xl">Photos</h1>
            <a class="px-4 bg-sky-900 text-white rounded-md" :href="route('admin.photos.create')">Create</a>
            <div class="flex flex-col">
                <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
                    <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
                        <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
                            <table class="min-w-full divide-y divide-gray-200">
                                <thead class="bg-gray-50">
                                    <tr>
                                        <th
                                            scope="col"
                                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
                                        >ID</th>
                                        <th
                                            scope="col"
                                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
                                        >Photos</th>
                                        <th
                                            scope="col"
                                            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
                                        >Description</th>
                                        <th scope="col" class="relative px-6 py-3">
                                            <span class="sr-only">Edit</span>
                                        </th>
                                    </tr>
                                </thead>
                                <tbody class="bg-white divide-y divide-gray-200">
                                    <tr v-for="photo in photos" :key="photo.id">
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div
                                                class="text-sm text-gray-900"
                                            >{{ photo.id }}</div>
                                        </td>

                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="flex items-center">
                                                <div class="flex-shrink-0 h-10 w-10">
                                                    <img
                                                        class="h-10 w-10 rounded-full"
                                                        :src="photo.path"
                                                        alt
                                                    />
                                                </div>
                                            </div>
                                        </td>

                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="text-sm text-gray-900">
                                              {{ photo.description.slice(0, 100) + '...' }}
                                            </div>
                                        </td>
                                      <!-- ACTIONS -->
                                        <td class="px-6 py-4 whitespace-nowrap text-right text-sm font-medium">
                                            <a href="#" class="text-indigo-600 hover:text-indigo-900">
                                            View - Edit - Delete
                                            </a>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
              </div>
          </div>
      </div>
  </app-layout>
</template>
  
  <script>
  import { defineComponent } from "vue";
  import AppLayout from "@/Layouts/AppLayout.vue";
  
  export default defineComponent({
    components: {
      AppLayout,
    },
    props: {
      photos: Array,
    },
  });
  </script>
  