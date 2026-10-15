<script lang="ts">
    import { t } from "$lib/i18n/translations";

    import SectionHeading from "$components/misc/SectionHeading.svelte";
</script>

<section id="summary">
<SectionHeading
    title={$t("about.heading.summary")}
    sectionId="summary"
/>

Este site, mantido pela PSDev Sistemas, salva o que você quiser dos seus sites favoritos: vídeos, áudios, fotos ou GIFs. Cole o link e pronto.

Um aplicativo web prático, que funciona em qualquer aparelho, sempre que você precisar.
</section>

<section id="privacy-efficiency">
<SectionHeading
    title={$t("about.heading.privacy_efficiency")}
    sectionId="privacy-efficiency"
/>

Os pedidos ao servidor de processamento não exigem conta, e as informações sobre os túneis de arquivo são criptografadas.
O servidor de processamento não grava registros dos downloads.

Quando um pedido precisa de processamento extra, como remux ou conversão, a mídia é processada
direto no seu aparelho. Isso garante mais eficiência e privacidade.

Se o seu aparelho não suportar processamento local, o servidor processa a mídia em tempo real.
Nesse caso, ela é transmitida direto para você, sem nunca ser gravada no disco do servidor.

Você pode [ativar o túnel forçado](/settings/privacy#tunnel) para aumentar ainda mais a privacidade.
Com ele, todos os arquivos passam pelo túnel, não só os que precisam.
Ninguém saberá de onde você baixou algo, nem o seu provedor de internet.
</section>

<section id="community">
<SectionHeading
    title={$t("about.heading.community")}
    sectionId="community"
/>

Este site é construído sobre o [cobalt](https://github.com/imputnet/cobalt), um projeto de código aberto criado pela [imput](https://imput.net/).
Veja os detalhes em [créditos e licenças](/about/credits).

Se alguém de confiança hospeda uma instância de processamento, peça o domínio e [adicione nos ajustes de instâncias](/settings/instances#community).
</section>
