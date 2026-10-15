<script lang="ts">
    // brand status glyph, replaces the original cobalt mascot art
    import type { MeowbaltEmotions } from "$lib/types/meowbalt";

    import IconBolt from "@tabler/icons-svelte/IconBolt.svelte";
    import IconInbox from "@tabler/icons-svelte/IconInbox.svelte";
    import IconHelp from "@tabler/icons-svelte/IconHelp.svelte";
    import IconAlertTriangle from "@tabler/icons-svelte/IconAlertTriangle.svelte";

    type Props = {
        emotion: MeowbaltEmotions;
        forceLoaded?: boolean;
    };

    const { emotion }: Props = $props();

    const icons = {
        error: IconAlertTriangle,
        question: IconHelp,
        think: IconInbox,
        fast: IconBolt,
    };
</script>

{#if emotion === "smile"}
    <span class="brand-glyph mark" aria-hidden="true">
        <img class="mark-light" src="/brand/mark.png" width="64" height="64" alt="" />
        <img class="mark-dark" src="/brand/mark-reverse.png" width="64" height="64" alt="" />
    </span>
{:else}
    {@const Icon = icons[emotion]}
    <span class="brand-glyph tile {emotion}" aria-hidden="true">
        <Icon />
    </span>
{/if}

<style>
    .brand-glyph {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-shrink: 0;
    }

    .mark img {
        display: block;
        width: 64px;
        height: 64px;
    }

    .mark-dark,
    :global([data-theme="dark"]) .mark-light {
        display: none !important;
    }

    :global([data-theme="dark"]) .mark-dark {
        display: block !important;
    }

    .tile {
        width: 56px;
        height: 56px;
        border-radius: 16px;
        color: var(--accent);
        background: var(--accent-soft);
        box-shadow: 0 0 0 1px var(--button-stroke) inset;
    }

    .tile :global(svg) {
        width: 28px;
        height: 28px;
        stroke-width: 1.6px;
    }

    .tile.error {
        color: var(--red);
        background: color-mix(in srgb, var(--red) 12%, transparent);
    }
</style>
