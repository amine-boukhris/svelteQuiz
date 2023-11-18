<script lang="ts">
    export let option: {
        label: string;
        text: string;
    };
    export let selectedOption: null | string;
    export let handleChangeOption: (label: string) => void;
    export let showCorrectAnswer: boolean;
    export let answer: string;
</script>

<!-- class="{selectedOption === option.label ? 'bg-yellow-300' : 'bg-gray-200'} rounded w-[49%] text-center p-2 mb-4 py-5" -->

<button
    class={`bg-gray-200 rounded w-[49%] text-center p-2 mb-4 py-5 ${
        selectedOption === option.label ? "bg-yellow-200" : null
    } ${
        showCorrectAnswer && (answer === option.label ? 'bg-green-400' : 'bg-red-500')
    }`}
    on:click={() => handleChangeOption(option.label)}
>
    {option.text}
</button>
