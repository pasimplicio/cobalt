<script lang="ts">
    import { browser } from "$app/environment";
    import SmallDialog from "$components/dialog/SmallDialog.svelte";
</script>

{#if !browser}
    <noscript style="display: contents">
        <div id="nojs-ack">
            <SmallDialog
                id="nojs-dialog"
                meowbalt="error"
                bodyText={
                    "Este site usa JavaScript para os downloads e para a interface, mas ele está desativado no seu navegador. "
                    + "Você ainda pode navegar pelas páginas, mas a maioria das funções não vai funcionar."
                }
                buttons={[
                    {
                        text: "Entendi",
                        main: true,
                        action: () => {},
                        link: "#nojs-ack"
                    },
                ]}
            />
            <div id="nojs-dialog-backdrop"></div>
        </div>
    </noscript>
{/if}

<style>
    :global(#nojs-ack) {
        display: contents;
    }

    :global(#nojs-ack:target) {
        display: none;
    }

    #nojs-dialog-backdrop {
        opacity: 1;
    }
</style>
