<script lang="ts">
    import * as images from '../image';
    import {goto} from '$app/navigation';


    interface Quiz {
        id: number;
        name: string;
        imageUrl: string;
        questions: {
            id: number;
            question: string;
            options: { id: number; text: string; label: string }[];
            answer: string;
        }[];
    }

    export let quiz: Quiz;

    const imageUrl = images[quiz.imageUrl as keyof typeof images];
</script>

    <button
        class="quiz-card shadow w-[250px] rounded overflow-hidden cursor-pointer m-2"
        on:click={() => goto(`/quiz/${quiz.id}`)}
    >
        <img src={imageUrl} alt="" class="h-44" />
        <div class="flex items-center justify-between py-3 px-2">
            <h1 class="font-bold">{quiz.name}</h1>
            <p>{quiz.questions.length} questions</p>
        </div>
    </button>
