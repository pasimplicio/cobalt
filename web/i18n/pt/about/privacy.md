<script lang="ts">
    import env from "$lib/env";
    import { t } from "$lib/i18n/translations";

    import SectionHeading from "$components/misc/SectionHeading.svelte";
</script>

<section id="general">
<SectionHeading
    title={$t("about.heading.general")}
    sectionId="general"
/>

A nossa política de privacidade é simples: não coletamos nem guardamos nada sobre você.
O que você faz é problema seu, não nosso nem de mais ninguém.

Estes termos valem apenas para a instância da PSDev Sistemas.
Em outras instâncias, procure quem as hospeda para ter informações precisas.
</section>

<section id="local">
<SectionHeading
    title={$t("about.heading.local")}
    sectionId="local"
/>

As ferramentas com processamento no aparelho funcionam offline, localmente,
e nunca enviam os dados processados para lugar nenhum.
Elas são sempre identificadas como tal.
</section>

<section id="saving">
<SectionHeading
    title={$t("about.heading.saving")}
    sectionId="saving"
/>

Ao salvar, pode ser preciso intermediar, fazer remux ou converter os arquivos.
Nesse caso, um túnel temporário é criado para isso
e o mínimo de informação necessária sobre a mídia fica guardado por 90 segundos.

**Todos os dados do túnel são criptografados com uma chave que só você tem.**

Os dados criptografados do túnel podem incluir:
- o nome do serviço de origem.
- as URLs originais dos arquivos de mídia.
- parâmetros internos para diferenciar os tipos de processamento.
- metadados mínimos do arquivo (nome gerado, título, autor, ano de criação, direitos autorais).
- informações mínimas sobre o pedido original, usadas caso uma URL falhe durante o túnel.

Esses dados são apagados da memória do servidor de forma irreversível após 90 segundos.
Ninguém tem acesso aos dados do túnel em cache, nem quem administra a instância.

A mídia que passa pelos túneis nunca é guardada nem fica em cache.
Tudo é processado em tempo real, inclusive o remux e a conversão.
Os túneis funcionam como um proxy anônimo.

Se o seu aparelho suporta processamento local,
os dados criptografados do túnel são ainda menores, porque a maior parte volta para você.

Veja o [código-fonte relacionado no GitHub](https://github.com/imputnet/cobalt/tree/main/api/src/stream)
para entender como funciona.
</section>

<section id="encryption">
<SectionHeading
    title={$t("about.heading.encryption")}
    sectionId="encryption"
/>

Os dados temporários do túnel são criptografados com o padrão AES-256.
As chaves de descriptografia vão apenas no link de acesso e nunca são registradas nem guardadas.
Só você tem acesso ao link e às chaves.
Uma chave única é gerada para cada túnel.
</section>

{#if env.PLAUSIBLE_ENABLED}
<section id="plausible">
<SectionHeading
    title={$t("about.heading.plausible")}
    sectionId="plausible"
/>

Usamos o [Plausible](https://plausible.io/) para saber, de forma totalmente anônima,
o número aproximado de usuários ativos. Nenhuma informação que identifique você
ou seus pedidos é guardada. Todos os dados são anonimizados e agregados.
A [instância do Plausible](https://{env.PLAUSIBLE_HOST}/) usada aqui é hospedada por nós.

O Plausible não usa cookies e segue a LGPD, o GDPR, o CCPA e o PECR.

Se não quiser participar das estatísticas anônimas, desative nos [ajustes de privacidade](/settings/privacy#analytics).
Com isso, o script do Plausible nem chega a ser carregado.

[Saiba mais sobre o compromisso do Plausible com a privacidade](https://plausible.io/privacy-focused-web-analytics).
</section>
{/if}
