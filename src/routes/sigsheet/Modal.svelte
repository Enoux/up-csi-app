<script lang="ts">
    const { name, role, closeModal, activeCategory } = $props();
    // Implement color of name

    const categoryColors: Record<string, string> = {
        Exec: 'var(--color-csi-blue)',
        'M&I': 'var(--color-mni-pink)',
        Service: 'var(--color-service-yellow)',
        Innov: 'var(--color-innov-orange)',
        Engg: 'var(--color-engg-blue)',
        Exte: 'var(--color-exte-blue)',
        'B&C': 'var(--color-bnc-green)',
    };
</script>

<main
    class="font-inter fixed inset-0 mx-[15vw] my-[15vh] items-center justify-center rounded-xl p-2 pb-6 shadow dark:bg-[#2f2f32]"
>
    <div class="mb-3 grid justify-items-end">
        <button aria-label="X" onclick={closeModal} class="text-csi-white hover:text-csi-blue cursor-pointer">
            <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="size-[30px] fill-current"
            >
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
            </svg>
        </button>
    </div>

    <div class="grid gap-6 md:grid-cols-2 md:gap-0">
        <div class="mx-10 md:mr-3">
            <h2 class="pb-1 text-4xl font-bold" style="color:{categoryColors[activeCategory]}">{name}</h2>
            <h3 class="dark:text-csi-white text-sm">{role}</h3>

            <form class="mt-4">
                <label for="question" class="dark:text-csi-white mb-1 block pt-5 text-2xl font-bold"
                    >Your Question</label
                >
                <textarea
                    id="question"
                    class="dark:text-csi-white mb-3 w-full rounded-xl px-4 py-2 text-sm font-light md:h-10 dark:bg-[#161619]"
                    placeholder="Type your question here ..."
                    style="height: 100px; resize: none"
                    required
                ></textarea>

                <label for="answer" class="dark:text-csi-white mb-1 block text-2xl font-bold">Their Answer</label>
                <textarea
                    id="answer"
                    class="dark:text-csi-white mb-3 w-full rounded-xl px-4 py-2 text-sm font-light md:h-10 dark:bg-[#161619]"
                    placeholder="Type their answer here ..."
                    style="height: 100px; resize: none"
                    required
                ></textarea>
            </form>
        </div>

        <div class="text-csi-black mx-10 flex flex-col items-center gap-7 md:ml-3">
            <div
                class="border-csi-blue flex h-[77%] w-[100%] flex-col items-center justify-center rounded-lg border-2 border-dashed p-10 text-center"
                style="background-color:rgba(0, 198, 215, 0.07);"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke-width="1.5"
                    stroke="#00C6D7"
                    class="size-30 justify-center"
                >
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M6.827 6.175A2.31 2.31 0 0 1 5.186 7.23c-.38.054-.757.112-1.134.175C2.999 7.58 2.25 8.507 2.25 9.574V18a2.25 2.25 0 0 0 2.25 2.25h15A2.25 2.25 0 0 0 21.75 18V9.574c0-1.067-.75-1.994-1.802-2.169a47.865 47.865 0 0 0-1.134-.175 2.31 2.31 0 0 1-1.64-1.055l-.822-1.316a2.192 2.192 0 0 0-1.736-1.039 48.774 48.774 0 0 0-5.232 0 2.192 2.192 0 0 0-1.736 1.039l-.821 1.316Z"
                    />
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M16.5 12.75a4.5 4.5 0 1 1-9 0 4.5 4.5 0 0 1 9 0ZM18.75 10.5h.008v.008h-.008V10.5Z"
                    />
                </svg>

                <p class="text-csi-blue">Drop file here or click to take a picture</p>
            </div>
            <button
                class="dark:bg-csi-blue bg-opacity-10 dark:hover:bg-innov-orange h-60px cursor-pointer rounded-full px-6 py-2 text-xl font-semibold"
            >
                Submit
            </button>
        </div>
    </div>
</main>
