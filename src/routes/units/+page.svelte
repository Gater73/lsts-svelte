<script lang="ts">
    import { browser } from '$app/environment'
    import UnitSelector from '$lib/UnitSelector.svelte';
    var unit:string|null = "";
    if (browser) {
        const queryString = window.location.search;
        const urlParams = new URLSearchParams(queryString);
        unit = urlParams.get('unit');
        console.log(typeof unit);
    }
</script>

<UnitSelector />
