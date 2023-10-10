<script setup></script>

<template>
  <main>
    <div
      class="flex-col flex w-full h-screen overflow-auto justify-start gap-5"
    >
      <header
        class="flex w-full px-40 py-3 justify-between font-semibold text-4xl border-b-[1px] mt-5"
      >
        <h1>Notes</h1>
        <button
          class="rounded-xl w-12 h-12 self-center text-center inline-block align-middle transition-all ease-in-out duration-100 active:text-3xl active:bg-black/5 active:text-black hover:bg-black/5 hover:text-black"
        >
          +
        </button>
      </header>
      <div class="flex px-40">
        <div
          class="group relative flex flex-col justify-between bg-pink-200 px-4 py-2 rounded-md w-[250px] h-full min-h-[200px] gap-5 hover:cursor-pointer hover:outline hover:outline-4 outline-black/10 outline-offset-4"
        >
          <div
            class="absolute invisible right-2 top-2 h-6 w-6 bg-black/70 rounded-full text-center text-sm text-white/90 group-hover:visible group-active:visible"
          >
            x
          </div>
          <p>henlo</p>
          <p class="text-black/50">date</p>
        </div>
      </div>
    </div>
  </main>
</template>
