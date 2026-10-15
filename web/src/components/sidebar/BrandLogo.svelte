<script>
    import { t } from "$lib/i18n/translations";
</script>

<a id="brand-logo" href="/" aria-label={$t("general.cobalt")}>
    <img
        src="/brand/mark-reverse.png"
        width="40"
        height="40"
        alt=""
        aria-hidden="true"
    />
</a>

<style>
    #brand-logo {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: calc(var(--sidebar-tab-padding) * 2) 0;

        /* accommodate space for scaling animation */
        padding-bottom: calc(var(--sidebar-tab-padding) * 2 - var(--sidebar-inner-padding));
        border-radius: var(--border-radius);
    }

    #brand-logo img {
        display: block;
        width: 40px;
        height: 40px;
        transition: transform 0.2s cubic-bezier(0.16, 1, 0.3, 1);
    }

    @media (hover: hover) {
        #brand-logo:hover img {
            transform: scale(1.06);
        }
    }

    :global([data-reduce-motion="true"]) #brand-logo img {
        transition: none;
    }

    @media screen and (max-width: 535px) {
        #brand-logo {
            display: none;
        }
    }
</style>
