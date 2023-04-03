<script lang="ts">
    export let content: string;
    export let completed: boolean;
</script>

<div class="w-full border border-neutral-300 shadow-sm p-3 rounded-md space-x-2">
    <input type="checkbox" 
    bind:checked="{completed}"
    class="cursor-pointer accent-purple-600" />
    <input  type="tex" bind:value="{content}" 
    disabled="{completed}"
    class="disabled:opacity-50 disabled:line-through" />
</div>