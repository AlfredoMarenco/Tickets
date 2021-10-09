<template>
  <app-layout title="Users">
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Users
      </h2>
    </template>

    <div class="py-12">
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
          <div class="p-6 sm:px-20 bg-white border-b border-gray-200">
            <Link :href="route('user.create')">
                    Crear usuario
            </Link>
            <table class="table-auto w-full">
              <thead>
                <tr>
                  <th class="p-3">ID</th>
                  <th class="p-3">Nombre</th>
                  <th class="p-3">Email</th>
                  <th class="p-3">Acciones</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="u in users" :key="u.id">
                  <td class="p-3">{{ u.id }}</td>
                  <td class="p-3">{{ u.name }}</td>
                  <td class="p-3">{{ u.email }}</td>
                  <td class="p-3"></td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </app-layout>
</template>

<script>
import { defineComponent } from "vue";
import AppLayout from "@/Layouts/AppLayout.vue";
import { Link } from '@inertiajs/inertia-vue3';

export default defineComponent({
  props: ["users"],
  components: {
    AppLayout,
    Link,
  },
});
</script>
