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

our privacy policy is simple: we don't collect or store anything about you.
what you do is solely your business, not ours or anyone else's.

these terms are applicable only to the PSDev Sistemas instance.
in other cases, you may need to contact the instance hoster for accurate info.
</section>

<section id="local">
<SectionHeading
    title={$t("about.heading.local")}
    sectionId="local"
/>

tools that use on-device processing work offline, locally,
and never send any processed data anywhere.
they are explicitly marked as such whenever applicable.
</section>

<section id="saving">
<SectionHeading
    title={$t("about.heading.saving")}
    sectionId="saving"
/>

when saving, files may need to be proxied or remuxed/transcoded.
if that's the case, a temporary tunnel is created for this purpose
and minimal required information about the media is stored for 90 seconds.

**all tunnel data is encrypted with a key that only you have access to.**

encrypted tunnel data may include:
- origin service's name.
- original URLs for media files.
- internal arguments needed to differentiate between types of processing.
- minimal file metadata (generated filename, title, author, creation year, copyright info).
- minimal information about the original request that may be used in case of an URL failure during the tunnelling process.

this data is irreversibly purged from the server's RAM after 90 seconds.
no one has access to cached tunnel data, not even instance owners.

media data from tunnels is never stored or cached anywhere.
everything is processed live, even during remuxing and transcoding.
tunnels function like an anonymous proxy.

if your device supports local processing,
the encrypted tunnel info includes way less, because most of it is returned to you instead.

see the [related source code on github](https://github.com/imputnet/cobalt/tree/main/api/src/stream)
to learn more about how it works.
</section>

<section id="encryption">
<SectionHeading
    title={$t("about.heading.encryption")}
    sectionId="encryption"
/>

temporarily stored tunnel data is encrypted using the AES-256 standard.
decryption keys are only included in the access link and never logged/cached/stored anywhere.
only you have access to the link & encryption keys.
keys are generated uniquely for each requested tunnel.
</section>

{#if env.PLAUSIBLE_ENABLED}
<section id="plausible">
<SectionHeading
    title={$t("about.heading.plausible")}
    sectionId="plausible"
/>

we use [plausible](https://plausible.io/) to get an approximate number
of active users, fully anonymously. no identifiable information about
you or your requests is ever stored. all data is anonymized and aggregated.
we self-host the [plausible instance](https://{env.PLAUSIBLE_HOST}/) used here.

plausible doesn't use cookies and is fully compliant with GDPR, CCPA, and PECR.

if you wish to opt out of anonymous analytics, you can do it in [privacy settings](/settings/privacy#analytics).
if you opt out, the plausible script will not be loaded at all.

[learn more about plausible's dedication to privacy](https://plausible.io/privacy-focused-web-analytics).
</section>
{/if}
