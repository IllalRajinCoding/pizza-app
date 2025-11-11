<script>
    import Hero from '$lib/components/Hero.svelte';
    import TentangKami from '$lib/components/About.svelte';
    import Produk from '$lib/components/Product.svelte';
    import Keunggulan from '$lib/components/Superiority.svelte';
    import Kontak from '$lib/components/Contact.svelte';
    import Banner from '$lib/components/Banner.svelte';
</script>

<svelte:head>
    <title>Amara Pizza Rumah - Pizza Homemade Cita Rasa Restoran</title>
    <meta name="description" content="Pesan pizza homemade otentik dari Amara Pizza Rumah. Dibuat fresh, bahan premium, halal, dan terjangkau." />
</svelte:head>

<Hero />
<Banner />
<TentangKami />
<Produk />
<Keunggulan />
<Kontak />