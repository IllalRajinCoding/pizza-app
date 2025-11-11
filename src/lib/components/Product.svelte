<script>
    // 1. STRUKTUR DATA BARU
    // Kita susun data produk sesuai kategori
    const categories = [
        {
            id: 'small',
            shortName: "Small Bite",
            fullName: "Amara Pizza Small Bite Baby",
            items: [
                {
                    name: "Small Bite (10cm - 14cm)",
                    toppings: "Sosis, keju, mayonaise, origano",
                    price: "Rp 5.000 - Rp 10.000"
                }
            ]
        },
        {
            id: 'medium',
            shortName: "Medium Bite",
            fullName: "Amara Pizza Medium Bite (16cm)",
            items: [
                { name: "Jagung", toppings: "Sosis, jagung, mayonaise, keju, origano", price: "Rp 25.000" },
                { name: "Bakso", toppings: "Sosis, bakso, mayonaise, keju, origano", price: "Rp 25.000" },
                { name: "Jamur", toppings: "Jamur, mayonaise, keju, origano", price: "Rp 28.000" },
                { name: "Full Keju", toppings: "Keju Amara, mayonaise, keju, origano", price: "Rp 28.000" },
                { name: "Paproni", toppings: "Paproni, mayonaise, keju, origano, bawang bombay", price: "Rp 32.000" }
            ]
        },
        {
            id: 'big',
            shortName: "Big Bite",
            fullName: "Amara Pizza Big Bite (20cm)",
            items: [
                { name: "Jagung", toppings: "Sosis, jagung, mayonaise, keju, origano", price: "Rp 50.000" },
                { name: "Bakso", toppings: "Sosis, bakso, mayonaise, keju, origano", price: "Rp 50.000" },
                { name: "Jamur", toppings: "Jamur, mayonaise, keju, origano", price: "Rp 55.000" },
                { name: "Full Keju", toppings: "Keju Amara, mayonaise, keju, origano", price: "Rp 55.000" },
                { name: "Paproni", toppings: "Paproni, mayonaise, keju, origano, bawang bombay", price: "Rp 65.000" }
            ]
        }
    ];
    let activeCategory = 'medium';
    $: activeCategoryData = categories.find(cat => cat.id === activeCategory) ?? categories[0];
    $: activeProducts = activeCategoryData?.items ?? [];

</script>

<section id="produk" class="py-24 bg-gray-100">
    <div class="container max-w-[1400px] mx-auto px-4">
        <div class="text-center max-w-3xl mx-auto mb-12">
            <h2 class="text-3xl md:text-4xl font-bold poppins text-gray-900">
                Pilihan 
                <span class="font-bold text-transparent bg-clip-text bg-linear-to-r from-orange-500 to-red-600">
                    Menu Pizza
                </span> Kami
            </h2>
            <p class="mt-4 text-lg text-gray-600">
                Pilih ukuran yang paling sesuai dengan seleramu. Dibuat fresh berdasarkan pesanan.
            </p>
        </div>

        <div class="flex justify-center items-center flex-wrap gap-3 md:gap-6 mb-12">
            {#each categories as category (category.id)}
                <button 
                    on:click={() => activeCategory = category.id}
                    class="font-semibold poppins px-6 py-3 rounded-lg text-lg transition-all duration-300 ease-in-out transform hover:scale-105 shadow-md"
                    
                    class:bg-red-600={activeCategory === category.id}
                    class:text-white={activeCategory === category.id}
                    class:bg-white={activeCategory !== category.id}
                    class:text-gray-700={activeCategory !== category.id}
                    class:hover:bg-red-700={activeCategory === category.id}
                    class:hover:bg-gray-200={activeCategory !== category.id}
                >
                    {category.shortName}
                </button>
            {/each}
        </div>

        <h3 class="text-2xl font-bold poppins text-gray-800 mb-8 text-center">
            Varian {activeCategoryData.fullName}
        </h3>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6 max-w-6xl mx-auto">
            {#each activeProducts as product (product.name)}
                <div class="bg-white rounded-xl shadow-lg overflow-hidden border border-gray-200 flex flex-col h-full">
                    <div class="p-6 grow">
                        <div class="mb-3">
                            <span class="text-sm bg-red-100 text-red-700 font-semibold px-3 py-1 rounded-full">
                                {activeCategoryData.shortName}
                            </span>
                        </div>
                        
                        <h4 class="text-xl font-semibold poppins text-gray-900 mb-3">{product.name}</h4>
                        
                        <div class="text-2xl font-bold poppins text-red-600 mb-4">
                            {product.price}
                        </div>
                        
                        <p class="text-gray-600 text-sm">
                            <strong class="text-gray-700">Topping:</strong> {product.toppings}
                        </p>
                    </div>

                    <div class="p-6 bg-gray-50 mt-auto">
                        <a href="https://wa.me/6285772091907?text=Hallo!%20Saya%20Order%20Varian%20{activeCategoryData.shortName}%20{product.name}" 
                           class="block w-full text-center bg-linear-to-r from-orange-500 to-red-600 text-white font-semibold px-5 py-3 rounded-lg hover:from-orange-600 hover:to-red-700 transition-all shadow-lg shadow-red-500/30">
                            Pesan Varian Ini
                        </a>
                    </div>
                </div>
            {/each}
        </div>

    </div>
</section>