<script setup>
import { ref } from "vue";

const modal = ref(false);
const createNote = ref("");
const notes = ref([]);
const bgColor = ref("bg-yellow-300");
const errorMassage = ref("");

function addNote() {
  if (createNote.value.length < 10) {
    return (errorMassage.value = "Notes should be 10 characters or longer");
  }
  notes.value.push({
    id: Math.floor(Math.random() * 1000000),
    text: createNote.value,
    date: new Date(),
    bgColor: bgColor.value,
  });
  modal.value = false;
  createNote.value = "";
  bgColor.value = "bg-yellow-300";
  errorMassage.value = "";
}
</script>

<template>
  <main class="relative">
    <div
      v-show="modal"
      class="w-full h-screen flex justify-center items-center absolute"
    >
      <div
        class="absolute w-full h-full bg-black/20 z-40"
        @click="modal = false"
      ></div>
      <div
        class="flex flex-col w-4/6 h-fit p-4 bg-slate-50 rounded-xl gap-5 z-50"
      >
        <textarea
          cols="30"
          rows="5"
          placeholder="Take a Note..."
          class="focus:outline-none bg-transparent"
          v-model="createNote"
        ></textarea>
        <p class="text-red-400" v-show="errorMassage">{{ errorMassage }}</p>
        <div class="flex gap-5 justify-between items-center">
          <div class="flex gap-5">
            <button
              @click="bgColor = 'bg-yellow-300'"
              class="h-[30px] w-[30px] rounded-full bg-yellow-300 hover:cursor-pointer hover:outline hover:outline-4 focus:outline focus:outline-4 outline-black/10 outline-offset-4"
            ></button>
            <button
              @click="bgColor = 'bg-pink-300'"
              class="h-[30px] w-[30px] rounded-full bg-pink-300 hover:cursor-pointer hover:outline hover:outline-4 focus:outline focus:outline-4 outline-black/10 outline-offset-4"
            ></button>
            <button
              @click="bgColor = 'bg-purple-300'"
              class="h-[30px] w-[30px] rounded-full bg-purple-300 hover:cursor-pointer hover:outline hover:outline-4 focus:outline focus:outline-4 outline-black/10 outline-offset-4"
            ></button>
            <button
              @click="bgColor = 'bg-sky-300'"
              class="h-[30px] w-[30px] rounded-full bg-sky-300 hover:cursor-pointer hover:outline hover:outline-4 focus:outline focus:outline-4 outline-black/10 outline-offset-4"
            ></button>
            <button
              @click="bgColor = 'bg-emerald-300'"
              class="h-[30px] w-[30px] rounded-full bg-emerald-300 hover:cursor-pointer hover:outline hover:outline-4 focus:outline focus:outline-4 outline-black/10 outline-offset-4"
            ></button>
          </div>

          <button
            class="flex items-center justify-center h-[50px] w-[100px] rounded-md text-black/50 font-semibold text-center hover:cursor-pointer hover:bg-black/10"
            @click="addNote"
          >
            Submit
          </button>
        </div>
      </div>
    </div>
    <div
      class="flex-col flex w-full h-screen overflow-auto justify-start gap-5"
    >
      <header
        class="flex w-full px-40 py-3 justify-between font-semibold text-4xl border-b-[1px] mt-5"
      >
        <h1>Notes</h1>
        <button
          class="rounded-xl w-12 h-12 flex justify-center items-center text-center transition-all ease-in-out duration-100 active:text-3xl active:bg-black/5 active:text-black hover:bg-black/5 hover:text-black"
          @click="modal = true"
        >
          +
        </button>
      </header>
      <div class="flex px-40 flex-wrap gap-10">
        <div
          v-for="v in notes"
          :class="v.bgColor"
          class="group relative flex flex-col justify-between px-4 py-2 rounded-md w-[250px] h-[250px] text-black/70 gap-5 hover:cursor-pointer hover:outline hover:outline-4 outline-black/10 outline-offset-4"
        >
          <!-- <div
            class="absolute invisible right-2 top-2 h-6 w-6 bg-black/70 rounded-full text-center text-sm text-white/90 group-hover:visible group-active:visible"
            
          >
            x
          </div> -->
          <p class="w-full h-full overflow-y-auto">{{ v.text }}</p>
          <p class="text-black/50">{{ v.date.toLocaleDateString("en-US") }}</p>
        </div>
      </div>
    </div>
  </main>
</template>
