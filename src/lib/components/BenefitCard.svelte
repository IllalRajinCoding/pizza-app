<script>
    // Komponen ini menerima 'data' dari komponen induknya
    export let data;

    // Kita siapkan kelas dasar untuk semua kartu
    const baseCardClass = "p-8 rounded-2xl shadow-xl w-full";

    // --- PERUBAHAN DI SINI ---
    // Kelas khusus untuk kartu highlight (Gradien Oranye-Merah)
    const highlightCardClass = "bg-gradient-to-br from-orange-500 to-red-600 shadow-red-500/30 border-2 border-orange-400 text-white";
    
    // Kelas khusus untuk kartu biasa (tetap sama, untuk kontras)
    const defaultCardClass = "bg-gray-50 border-2 border-gray-200 text-gray-900";
</script>

<div class="{baseCardClass} {data.isHighlight ? highlightCardClass : defaultCardClass}">
    
    <h3 class="text-2xl md:text-3xl font-semibold poppins mb-6 {data.isHighlight ? 'text-white text-center' : 'text-gray-900'}">
        {data.title}
    </h3>

    <ul class="space-y-4">
        {#each data.items as item}
            <li class="flex items-start">
                
                <span class="w-8 shrink-0 text-center text-xl mr-2 {data.isHighlight ? 'text-amber-200' : 'text-red-600'}">
                    <i class="{item.icon}"></i>
                </span>
                
                <span class="text-lg {data.isHighlight ? 'text-gray-100' : 'text-gray-700'}">
                    {@html item.text}
                </span>
            </li>
        {/each}
    </ul>
</div>