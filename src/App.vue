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
          class="rounded-full bg-yellow-300 w-12 h-12 self-center text-center inline-block align-middle transition-all ease-in-out duration-100 active:text-3xl active:bg-black active:text-yellow-300 hover:bg-black hover:text-yellow-300"
        >
          +
        </button>
      </header>
      <div class="flex px-40">
        <div
          class="flex flex-col justify-between bg-pink-200 px-4 py-3 rounded-md w-[250px] h-full min-h-[200px] gap-5"
        >
          <p>henlo</p>
          <p class="text-black/50">date</p>
        </div>
      </div>
    </div>
  </main>
</template>
