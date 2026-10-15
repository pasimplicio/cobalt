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

this site is a modified version of [cobalt](https://github.com/imputnet/cobalt),
made and maintained by [imput](https://imput.net/). all credit for the original project goes to them.

PSDev Sistemas adapted the interface, translated it to portuguese,
and applied its own visual identity. this version is not affiliated with or endorsed by imput.
</section>

<section id="licenses">
<SectionHeading
    title={$t("about.heading.licenses")}
    sectionId="licenses"
/>

cobalt api (processing server) code is open source and licensed under [AGPL-3.0]({docs.apiLicense}).

cobalt frontend code is licensed under [CC-BY-NC-SA 4.0]({docs.webLicense}).
this modified version follows the same license and is not used for commercial purposes.

the project relies on many open source libraries.
you can see the full list of dependencies on [github]({contacts.github}).
</section>
