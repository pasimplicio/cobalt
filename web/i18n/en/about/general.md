<script lang="ts">
    import { t } from "$lib/i18n/translations";

    import SectionHeading from "$components/misc/SectionHeading.svelte";
</script>

<section id="summary">
<SectionHeading
    title={$t("about.heading.summary")}
    sectionId="summary"
/>

this site, run by PSDev Sistemas, helps you save anything from your favorite websites: video, audio, photos or gifs. just paste the link and you're done.

a convenient web app that works anywhere, whenever you need it.
</section>

<section id="privacy-efficiency">
<SectionHeading
    title={$t("about.heading.privacy_efficiency")}
    sectionId="privacy-efficiency"
/>

requests to the processing server don't require an account, and all information about file tunnels is encrypted.
the processing server doesn't keep download logs.

if a request requires additional processing, such as remuxing or transcoding, media is processed
directly on your device. this ensures best efficiency and privacy.

if your device doesn't support local processing, server-based live processing is used instead.
in this scenario, processed media is streamed directly to you, without ever being stored on the server's disk.

you can [enable forced tunneling](/settings/privacy#tunnel) to boost privacy even further.
when enabled, all downloaded files are tunneled, not just those that require it.
no one will know where you download something from, not even your network provider.
</section>

<section id="community">
<SectionHeading
    title={$t("about.heading.community")}
    sectionId="community"
/>

this site is built on [cobalt](https://github.com/imputnet/cobalt), an open source project made by [imput](https://imput.net/).
see [thanks & licenses](/about/credits) for details.

if someone you trust hosts a processing instance, ask them for a domain and [add it in instance settings](/settings/instances#community).
</section>
