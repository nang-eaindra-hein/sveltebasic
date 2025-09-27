<script lang='ts'>
    let temp=89;
</script>

{#if temp>100}
<p>too hot</p>
{:else if temp<80}
<p>too cold</p>
{:else}
<p>just right</p>

{/if}


