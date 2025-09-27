<script lang='ts'>
    import { page } from '$app/stores';  //reactive declaration (auto-update code)
    const productId = $page.params.productId;   
</script>

<h1>This is product details of id: {productId}</h1>  <!-- dynamic route -->