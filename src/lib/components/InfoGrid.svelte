<script lang="ts">
    export let data: { title: string, content: string | string[] }[] = [];
</script>

<div class="grid grid-cols-2 items-start justify-between w-full mt-2 gap-y-4">
    {#each data as item}
        <h4 class="h4">{item.title}:</h4>
        {#if Array.isArray(item.content)}
            <ul class="text-right">
                {#each item.content as subItem}
                    <li><h4 class="h4">{@html subItem}</h4></li>
                {/each}
            </ul>
        {:else}
            <h4 class="h4 text-right">{@html item.content}</h4>
        {/if}
    {/each}
</div>