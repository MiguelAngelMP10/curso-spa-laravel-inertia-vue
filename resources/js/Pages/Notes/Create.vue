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
              <h3 class="text-lg text-gray-900">Crear una nota</h3>
              <p class="text-sm text-gray-600">
                Luego de crear la podrás editar
              </p>
            </div>
          </div>
          <div class="md:col-span-2 mt-5 md:mt-0">
            <div class="shadow bg-white md:rounded-md p-4">
              <form @submit.prevent="submit">
                <label class="block font-medium text-sm text-gray-700">
                  Resumen
                </label>
                <textarea
                  class="form-input w-full rounded-md shadow-sm"
                  v-model="form.excerpt"
                ></textarea>
                <label class="block font-medium text-sm text-gray-700">
                  Contenido
                </label>
                <textarea
                  class="form-input w-full rounded-md shadow-sm"
                  v-model="form.content"
                  rows="8"
                ></textarea>
                <button
                  class="
                    bg-transparent
                    hover:bg-green-500
                    text-grebg-green-700
                    font-semibold
                    hover:text-white
                    py-2
                    px-4
                    border border-grebg-green-500
                    hover:border-transparent
                    rounded
                  "
                >
                  Crear
                </button>
              </form>
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
  data() {
    return {
      form: {
        excerpt: "",
        content: "",
      },
    };
  },
  methods: {
    submit() {
      this.$inertia.post(this.route("notes.update", this.note.id), this.form);
    },
  },
};
</script>
