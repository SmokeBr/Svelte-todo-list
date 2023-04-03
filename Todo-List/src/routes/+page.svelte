<script lang="ts">
// @ts-nocheck
import Task from "../lib/Task.svelte";

interface ITask {
    text: string;
    completed: boolean;
}

let tasks: ITask[] = [
    {
        text: "Tarefas de rotina estudos",
        completed: false,
    },
    {
        text: "Segunda Tarefa",
        completed: true,
    },
];

function addTask() {
    tasks = [
        ...tasks,
        {
            text: "My task create",
            completed: false,
        },
    ];
}
</script>

<div class="p-4 h-screen flex justify-center items-center flex-col space-y-2 max-w-lg mx-auto">
    {#each tasks as task}
        <Task bind:content="{task.text}" bind:completed="{task.completed}" />
    {/each}

    <button class="w-full flex justify-center space-x-2 text-neutral-500 border-2 border-neutral-300 p-3 rounded-lg border-dashed font-semibold"
    on:click="{addTask}"
    >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
            <path fill-rule="evenodd" d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25zM12.75 9a.75.75 0 00-1.5 0v2.25H9a.75.75 0 000 1.5h2.25V15a.75.75 0 001.5 0v-2.25H15a.75.75 0 000-1.5h-2.25V9z" clip-rule="evenodd" 
            />
          </svg>
          <span>Add Task</span>
        </button>
</div>