<h2>Find ACL URL</h2>
<label>
    document URL
    <input type="text" placeholder="https://you.solid.community/some/document" bind:value="docUrl">
</label>
<p>
{#await aclUrl}
    ...
{:then aclUrl}
    {aclUrl}
{:catch error}
    {error}
{/await}
</p>

<script>
import { aclUrl } from 'wac';

export default {
    data() {
        return {
            docUrl: ''
        }
    },
    computed: {
        aclUrl({ docUrl }) {
            return docUrl ? aclUrl(docUrl) : '';
        }
    }
}
</script>
