<script lang="ts">
    import { contacts, docs } from "$lib/env";
    import { t } from "$lib/i18n/translations";

    import SectionHeading from "$components/misc/SectionHeading.svelte";
</script>

<section id="imput">
<SectionHeading
    title="cobalt"
    sectionId="imput"
/>

Este site é uma versão modificada do [cobalt](https://github.com/imputnet/cobalt),
criado e mantido pela [imput](https://imput.net/). Todo o mérito do projeto original é deles.

A PSDev Sistemas adaptou a interface, traduziu o site para o português
e aplicou a própria identidade visual. Esta versão não é afiliada à imput nem endossada por ela.
</section>

<section id="licenses">
<SectionHeading
    title={$t("about.heading.licenses")}
    sectionId="licenses"
/>

O código da API do cobalt (servidor de processamento) é aberto e licenciado sob a [AGPL-3.0]({docs.apiLicense}).

O código da interface do cobalt é licenciado sob a [CC-BY-NC-SA 4.0]({docs.webLicense}).
Esta versão modificada segue a mesma licença e não tem fins comerciais.

O projeto usa muitas bibliotecas de código aberto.
A lista completa de dependências está no [GitHub]({contacts.github}).
</section>
