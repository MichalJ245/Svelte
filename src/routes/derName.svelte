<script lang="ts">
	import { twMerge } from 'tailwind-merge';
	interface zwischenGesicht
    {
        artikel?: string;
        Wort: string;
        Farbe?: string;
    }
    let
    {
        Wortschatz
    }:
    {
        Wortschatz: Array<zwischenGesicht>;
    } = $props();
</script>

<div
	id="main"
	class="max-w-max max-h-screen flex flex-col mx-auto shadow-2xl rounded-[50px] p-10 border-solid border-1 border-gray-200 outline-10 outline-white mb-40"
>
	{#each  Wortschatz as Stichwort}
        <div class="{Stichwort.Farbe}">
            {Stichwort.artikel}
            {Stichwort.Wort}
        </div>
    {/each}
</div>
