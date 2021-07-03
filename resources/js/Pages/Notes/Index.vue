<template>
  <app-layout>
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">
        Módulo de Notas
      </h2>
    </template>

    <div class="py-12">
      <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="md:grid md:grid-cols-3 md:gap-6">
          <div class="md:col-span-1">
            <div class="px-4 sm:px0">
              <h3 class="text-lg text-gray-900">Listado de notas</h3>
              <p class="text-sm text-gray-600">
                Toma el registro correcto y ejecuta cualquier función (ver,
                editar o eliminar)
              </p>
            </div>
          </div>
          <div class="md:col-span-2 mt-5 md:mt-0">
            <div class="shadow bg-white md:rounded-md">
              <inertia-link
                :href="route('notes.create')"
                class="
                  bg-transparent
                  hover:bg-green-500
                  text-green-700
                  font-semibold
                  hover:text-white
                  py-2
                  px-4
                  border border-green-500
                  hover:border-transparent
                  rounded
                "
              >
                Crear
              </inertia-link>
              <table class="pt-5">
                <tr v-for="(note, i) in notes" :key="i">
                  <td class="border px-4 py-2">
                    {{ note.excerpt }}
                  </td>
                  <td class="px-4 py-2">
                    <inertia-link
                      :href="route('notes.show', note.id)"
                      class="
                        bg-transparent
                        hover:bg-blue-500
                        text-blue-700
                        font-semibold
                        hover:text-white
                        py-2
                        px-4
                        border border-blue-500
                        hover:border-transparent
                        rounded
                      "
                    >
                      Ver
                    </inertia-link>
                  </td>
                  <td class="px-4 py-2">
                    <inertia-link
                      :href="route('notes.edit', note.id)"
                      class="
                        bg-transparent
                        hover:bg-green-500
                        text-green-700
                        font-semibold
                        hover:text-white
                        py-2
                        px-4
                        border border-green-500
                        hover:border-transparent
                        rounded
                      "
                    >
                      Editar
                    </inertia-link>
                  </td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </app-layout>
</template>

<script>
import AppLayout from "@/Layouts/AppLayout";
export default {
  components: {
    AppLayout,
  },
  props: {
    notes: Array,
  },
};
</script>
