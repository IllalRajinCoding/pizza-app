<script>
    import banner from '$lib/images/hero-banner.png';
</script>

<section 
    id="home"
    class="relative min-h-[60vh] md:min-h-[70vh] flex items-center overflow-hidden text-white"
    style="background-image: url({banner}); background-size: cover; background-position: center;"
>
    <div class="absolute inset-0 bg-black/20 z-0"></div>

    <div class="container max-w-[1400px] mx-auto px-4 py-20 z-10 relative">
        <div class="max-w-3xl text-center md:text-left">
            <h2 class="text-4xl md:text-6xl font-bold poppins text-white leading-tight">
                Cita Rasa Pizza Otentik,
                <span class="block text-orange-400">Hangat dari Dapur Rumah</span>
            </h2>
            <p class="mt-6 text-lg text-gray-200 max-w-2xl">
                Dibuat <strong class="font-semibold text-white">fresh from the oven</strong> dengan adonan lembut, bahan-bahan premium, dan resep orisinal yang menggugah selera.
            </p>
            
            <div class="mt-10 flex flex-col sm:flex-row gap-4 justify-center md:justify-start">
                <a 
                    href="#produk" 
                    class="bg-linear-to-r from-orange-500 to-red-600 text-white font-semibold px-8 py-3 rounded-lg 
                           hover:from-orange-600 hover:to-red-700 transition-all text-lg 
                           shadow-lg shadow-red-500/30"
                >
                    Lihat Menu
                </a>
                
                <a 
                    href="#kontak" 
                    class="bg-white text-gray-800 font-semibold px-8 py-3 rounded-lg 
                           hover:bg-gray-100 transition-all text-lg border border-gray-300"
                >
                    Hubungi Kami
                </a>
            </div>
        </div>
    </div>
</section>