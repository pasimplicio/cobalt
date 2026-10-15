<script>
    import { t } from "$lib/i18n/translations";

    import Omnibox from "$components/save/Omnibox.svelte";
    import SupportedServices from "$components/save/SupportedServices.svelte";
</script>

<svelte:head>
    <title>{$t("general.cobalt")}</title>
    <meta property="og:title" content={$t("general.cobalt")} />
</svelte:head>

<div id="cobalt-save-container" class="center-column-container">
    <SupportedServices />
    <main
        id="cobalt-save"
        tabindex="-1"
        data-first-focus
    >
        <h1 id="brand-lockup">
            <img
                class="lockup-light"
                src="/brand/logo.png"
                width="900"
                height="545"
                alt={$t("general.cobalt")}
            />
            <img
                class="lockup-dark"
                src="/brand/logo-reverse.png"
                width="900"
                height="545"
                alt=""
                aria-hidden="true"
            />
        </h1>
        <Omnibox />
    </main>
    <div id="terms-note">
        {$t("save.terms.note.agreement")}
        <a href="/about/terms">{$t("save.terms.note.link")}</a>
    </div>
</div>

<style>
    #cobalt-save-container {
        padding: var(--padding);
        overflow: hidden;
    }

    #cobalt-save {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
        gap: 28px;
    }

    #brand-lockup {
        display: flex;
        margin: 0;
        width: clamp(180px, 34vw, 248px);
        aspect-ratio: 900 / 545;
    }

    #brand-lockup img {
        width: 100%;
        height: auto;
        display: block;
    }

    .lockup-dark,
    :global([data-theme="dark"]) .lockup-light {
        display: none !important;
    }

    :global([data-theme="dark"]) .lockup-dark {
        display: block !important;
    }

    @media (prefers-reduced-motion: no-preference) {
        :global([data-reduce-motion="false"]) #brand-lockup {
            animation: lockup-in 0.6s cubic-bezier(0.16, 1, 0.3, 1) both;
        }
    }

    @keyframes lockup-in {
        from {
            opacity: 0;
            transform: translateY(6px) scale(0.985);
        }
    }

    #terms-note {
        bottom: 0;
        color: var(--gray);
        font-size: 12px;
        text-align: center;
        padding-bottom: 6px;
        font-weight: 500;
    }

    @media screen and (max-width: 535px) {
        #cobalt-save-container {
            padding-top: calc(var(--padding) / 2);
        }

        #cobalt-save {
            gap: 20px;
        }

        #terms-note {
            font-size: 11px;
            padding-bottom: 0;
        }
    }
</style>
