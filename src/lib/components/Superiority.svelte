<script>
    import BenefitCard from '$lib/components/BenefitCard.svelte';

    /**
     * State untuk melacak kartu aktif di desktop.
     */
    let activeCard = 'kelebihan';

    /**
     * SATU SUMBER DATA (Single Source of Truth).
     * Semua konten kartu didefinisikan di sini.
     * Ikon menggunakan kelas Font Awesome 6.
     */
    const cardData = [
        {
            id: 'kelebihan',
            title: 'Kelebihan Kami',
            isHighlight: true, // Ini adalah kartu utama (gradien oranye-merah)
            items: [
                { icon: 'fa-solid fa-fire-flame-curved', text: 'Dibuat <strong>fresh from the oven</strong> setiap pesanan.' },
                { icon: 'fa-solid fa-leaf', text: 'Menggunakan 100% bahan lokal berkualitas tinggi.' },
                { icon: 'fa-solid fa-palette', text: 'Banyak varian rasa dan tersedia custom topping.' },
                { icon: 'fa-solid fa-box-open', text: 'Tersedia pizza party box untuk acara spesial Anda.' },
                { icon: 'fa-solid fa-star', text: 'Resep orisinal yang tidak bisa ditemukan di tempat lain.' }
            ]
        },
        {
            id: 'keuntungan',
            title: 'Keuntungan Membeli',
            isHighlight: false,
            items: [
                { icon: 'fa-solid fa-pizza-slice', text: '<strong>Harga Terjangkau:</strong> Kualitas premium, harga bersahabat.' },
                { icon: 'fa-solid fa-truck-fast', text: '<strong>Layanan Antar Cepat:</b> Pizza dikirim hangat ke rumah Anda.' },
                { icon: 'fa-solid fa-circle-check', text: '<strong>Kualitas Terjamin:</strong> Menggunakan bahan segar dan halal.' },
                { icon: 'fa-solid fa-heart', text: '<strong>Cita Rasa Unik:</strong> Perpaduan resep Italia dan selera Nusantara.' },
                { icon: 'fa-solid fa-store', text: '<strong>Dukungan UMKM Lokal:</strong> Membantu tumbuhnya ekonomi rumahan.' }
            ]
        },
        {
            id: 'kompetitif',
            title: 'Keunggulan Kompetitif',
            isHighlight: false,
            items: [
                { icon: 'fa-solid fa-trophy', text: '<strong>Homemade Quality, Restaurant Taste.</strong>' },
                { icon: 'fa-solid fa-handshake-angle', text: 'Brand Lokal yang Peduli Pelanggan.' },
                { icon: 'fa-solid fa-lightbulb', text: 'Inovatif dan Fleksibel dengan menu baru.' },
                { icon: 'fa-solid fa-earth-asia', text: 'Kemasan Ramah Lingkungan.' },
                { icon: 'fa-solid fa-mobile-screen-button', text: 'Kehadiran Online yang Kuat (Website, WA, Social Media).' }
            ]
        }
    ];

    // Kita pisahkan data untuk desktop agar lebih mudah dibaca di HTML
    const kelebihan = cardData.find(c => c.id === 'kelebihan');
    const keuntungan = cardData.find(c => c.id === 'keuntungan');
    const kompetitif = cardData.find(c => c.id === 'kompetitif');
</script>

<section id="keunggulan" class="py-24 bg-white overflow-hidden perspective-[1000px]">
    <div class="container max-w-[1400px] mx-auto px-4">
        <div class="text-center max-w-3xl mx-auto mb-16 md:mb-20">
            <h2 class="text-3xl md:text-4xl font-bold poppins text-gray-900">
                Kenapa Harus 
                <span class="font-bold text-transparent bg-clip-text bg-linear-to-r from-orange-500 to-red-600">
                    Amara Pizza?
                </span>
            </h2>
            <p class="mt-4 text-lg text-gray-600">
                Kami tidak hanya menjual pizza, kami memberikan pengalaman rasa yang otentik dan pelayanan dari hati.
            </p>
        </div>

        <div class="grid grid-cols-1 gap-8 md:hidden">
            {#each cardData as card (card.id)}
                <BenefitCard data={card} />
            {/each}
        </div>

        <div class="hidden md:block relative max-w-4xl mx-auto h-[550px]">
            
            <div 
                class="absolute left-0 top-1/2 -translate-y-1/2 w-full md:w-[85%] origin-center 
                       cursor-pointer transition-all duration-500 ease-in-out transform-3d"
                class:z-30={activeCard === 'keuntungan'}
                class:scale-105={activeCard === 'keuntungan'}
                class:rotate-0={activeCard === 'keuntungan'}
                class:z-0={activeCard !== 'keuntungan'}
                class:scale-100={activeCard !== 'keuntungan'}
                class:-rotate-6={activeCard !== 'keuntungan'}
                on:click={() => activeCard = 'keuntungan'}
                on:keydown={(e) => e.key === 'Enter' && (activeCard = 'keuntungan')}
                role="button"
                tabindex="0"
            >
                <BenefitCard data={keuntungan} />
            </div>

            <div 
                class="absolute right-0 top-1/2 -translate-y-1/2 w-full md:w-[85%] origin-center
                       cursor-pointer transition-all duration-500 ease-in-out transform-3d"
                class:z-30={activeCard === 'kompetitif'}
                class:scale-105={activeCard === 'kompetitif'}
                class:rotate-0={activeCard === 'kompetitif'}
                class:z-0={activeCard !== 'kompetitif'}
                class:scale-100={activeCard !== 'kompetitif'}
                class:rotate-6={activeCard !== 'kompetitif'}
                on:click={() => activeCard = 'kompetitif'}
                on:keydown={(e) => e.key === 'Enter' && (activeCard = 'kompetitif')}
                role="button"
                tabindex="0"
            >
                <BenefitCard data={kompetitif} />
            </div>

            <div 
                class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 w-full md:w-[90%]
                       cursor-pointer transition-all duration-500 ease-in-out transform-3d"
                class:z-30={activeCard === 'kelebihan'}
                class:scale-110={activeCard === 'kelebihan'} class:z-10={activeCard !== 'kelebihan'}
                class:scale-95={activeCard !== 'kelebihan'}
                on:click={() => activeCard = 'kelebihan'}
                on:keydown={(e) => e.key === 'Enter' && (activeCard = 'kelebihan')}
                role="button"
                tabindex="0"
            >
                <BenefitCard data={kelebihan} />
            </div>
        </div>
    </div>
</section>