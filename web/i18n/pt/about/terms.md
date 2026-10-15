<script lang="ts">
    import { t } from "$lib/i18n/translations";
    import SectionHeading from "$components/misc/SectionHeading.svelte";
</script>

<section id="general">
<SectionHeading
    title={$t("about.heading.general")}
    sectionId="general"
/>

Estes termos valem apenas para a instância da PSDev Sistemas.
Em outras instâncias, procure quem as hospeda para ter informações precisas.
</section>

<section id="saving">
<SectionHeading
    title={$t("about.heading.saving")}
    sectionId="saving"
/>

A função de salvar facilita baixar conteúdo da internet,
e não temos nenhuma responsabilidade sobre o uso que se faz do conteúdo salvo.

Os servidores de processamento funcionam como proxies avançados e nunca gravam o conteúdo pedido em disco.
Tudo é tratado na memória e apagado de vez quando o túnel termina.
Não mantemos registros de downloads e não temos como identificar ninguém.

Saiba mais sobre como os túneis funcionam na [política de privacidade](/about/privacy).
</section>

<section id="responsibility">
<SectionHeading
    title={$t("about.heading.responsibility")}
    sectionId="responsibility"
/>

Você (usuário final) é responsável pelo que faz com nossas ferramentas e por como usa e distribui o conteúdo obtido.
Tenha cuidado ao usar conteúdo de outras pessoas e sempre dê crédito aos criadores originais.
Não viole termos de uso nem licenças.

Em usos educacionais, sempre cite as fontes e dê crédito aos criadores originais.

Uso justo e crédito fazem bem para todo mundo.
</section>

<section id="abuse">
<SectionHeading
    title={$t("about.heading.abuse")}
    sectionId="abuse"
/>

Como o serviço é totalmente anônimo, não temos como detectar abusos automaticamente.
Se você souber de alguma atividade abusiva, entre em contato com a PSDev Sistemas e faremos o possível para agir manualmente.
</section>
