<script lang="ts">
    import { onDestroy } from "svelte";
    import { t } from "$lib/i18n/translations";
    import { hapticSwitch } from "$lib/haptics";
    import { savingHandler } from "$lib/api/saving-handler";
    import { downloadButtonState } from "$lib/state/omnibox";

    import type { CobaltDownloadButtonState } from "$lib/types/omnibox";

    import IconCheck from "@tabler/icons-svelte/IconCheck.svelte";
    import IconLoader2 from "@tabler/icons-svelte/IconLoader2.svelte";
    import IconArrowRight from "@tabler/icons-svelte/IconArrowRight.svelte";
    import IconExclamationMark from "@tabler/icons-svelte/IconExclamationMark.svelte";

    export let url: string;
    export let disabled = false;
    export let loading = false;

    type DownloadButtonState = "idle" | "think" | "check" | "done" | "error";

    let buttonState: DownloadButtonState = "idle";
    $: buttonAltText = $t("a11y.save.download");

    const icons = {
        idle: IconArrowRight,
        think: IconLoader2,
        check: IconLoader2,
        done: IconCheck,
        error: IconExclamationMark,
    };

    const unsubscribe = downloadButtonState.subscribe(
        (state: CobaltDownloadButtonState) => {
            disabled = state !== "idle";
            loading = state === "think" || state === "check";
            buttonState = state;

            buttonAltText = $t(
                {
                    idle: "a11y.save.download",
                    think: "a11y.save.download.think",
                    check: "a11y.save.download.check",
                    done: "a11y.save.download.done",
                    error: "a11y.save.download.error",
                }[state]
            );

            // states that don't wait for anything, and thus can
            // transition back to idle after some period of time.
            const final: DownloadButtonState[] = ["done", "error"];
            if (final.includes(state)) {
                setTimeout(() => downloadButtonState.set("idle"), 1500);
            }
        }
    );

    onDestroy(() => unsubscribe());
</script>

<button
    id="download-button"
    class="state-{buttonState}"
    {disabled}
    on:click={() => {
        hapticSwitch();
        savingHandler({ url });
    }}
    aria-label={buttonAltText}
>
    <svelte:component this={icons[buttonState]} />
</button>

<style>
    #download-button {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-shrink: 0;

        height: 36px;
        width: 40px;
        padding: 0;

        border-radius: calc(var(--border-radius) - 4px);
        background: var(--accent);
        color: var(--on-accent);
        box-shadow: 0 4px 12px -6px var(--accent-glow);

        transition:
            background-color 0.15s,
            transform 0.15s cubic-bezier(0.16, 1, 0.3, 1);
    }

    #download-button :global(svg) {
        width: 20px;
        height: 20px;
        stroke-width: 2.2px;
    }

    #download-button:dir(rtl) :global(svg) {
        transform: scale(-1, 1);
    }

    .state-think :global(svg),
    .state-check :global(svg) {
        animation: spinner 0.7s infinite linear;
    }

    #download-button.state-error {
        background: var(--red);
    }

    #download-button.state-done {
        background: var(--green);
    }

    #download-button:disabled {
        cursor: unset;
    }

    #download-button:focus-visible {
        outline: 2px solid var(--secondary);
        outline-offset: 2px;
    }

    @media (hover: hover) {
        #download-button:hover:not(:disabled) {
            background: var(--accent-hover);
        }
    }

    #download-button:active:not(:disabled) {
        background: var(--accent-press);
        transform: scale(0.95);
    }

    :global([data-reduce-motion="true"]) #download-button,
    :global([data-reduce-motion="true"]) #download-button:active {
        transition: none;
        transform: none;
    }
</style>
