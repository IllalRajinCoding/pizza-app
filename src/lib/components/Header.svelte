<script>
    let mobileMenuOpen = false;

    function toggleMobileMenu() {
        mobileMenuOpen = !mobileMenuOpen;
    }

    function closeMobileMenu() {
        mobileMenuOpen = false;
    }
</script>

<header class="sticky top-0 left-0 w-full bg-white/80 backdrop-blur-sm shadow-sm z-50">
    <div class="max-w-[1400px] mx-auto w-full flex items-center justify-between px-4 py-6">
    
        <a href="/">
            <h1 class="text-2xl font-bold poppins">Amara <span class="text-indigo-400">P</span><span class="text-red-500">i</span><span class="text-yellow-500">zz</span><span class="text-red-400">a</span></h1>
        </a>

        <!-- Desktop Navigation -->
        <nav class="hidden md:flex items-center gap-6">
            <a href="#tentang" class="font-medium text-gray-600 hover:text-indigo-500 transition-colors">Tentang Kami</a>
            <a href="#produk" class="font-medium text-gray-600 hover:text-indigo-500 transition-colors">Menu Pizza</a>
            <a href="#keunggulan" class="font-medium text-gray-600 hover:text-indigo-500 transition-colors">Keunggulan</a>
            <a href="#kontak" class="font-medium text-gray-600 hover:text-indigo-500 transition-colors">Kontak</a>
        </nav>

        <a href="#produk" class="hidden md:inline-block bg-indigo-500 text-white font-semibold px-5 py-2 rounded-lg hover:bg-indigo-600 transition-shadow shadow-lg shadow-indigo-500/20">
            Pesan Sekarang
        </a>

        <!-- Mobile Menu Button -->
        <button 
            on:click={toggleMobileMenu}
            class="md:hidden p-2 text-gray-600 hover:text-indigo-500 focus:outline-none"
            aria-label="Toggle menu"
        >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                {#if mobileMenuOpen}
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                {:else}
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                {/if}
            </svg>
        </button>
    </div>

    <!-- Mobile Navigation Menu -->
    {#if mobileMenuOpen}
        <div class="md:hidden border-t border-gray-200 bg-white/95 backdrop-blur-sm">
            <nav class="max-w-[1400px] mx-auto px-4 py-4 flex flex-col gap-3">
                <a 
                    href="#tentang" 
                    on:click={closeMobileMenu}
                    class="font-medium text-gray-600 hover:text-indigo-500 transition-colors py-2 px-3 rounded-lg hover:bg-indigo-50"
                >
                    Tentang Kami
                </a>
                <a 
                    href="#produk" 
                    on:click={closeMobileMenu}
                    class="font-medium text-gray-600 hover:text-indigo-500 transition-colors py-2 px-3 rounded-lg hover:bg-indigo-50"
                >
                    Menu Pizza
                </a>
                <a 
                    href="#keunggulan" 
                    on:click={closeMobileMenu}
                    class="font-medium text-gray-600 hover:text-indigo-500 transition-colors py-2 px-3 rounded-lg hover:bg-indigo-50"
                >
                    Keunggulan
                </a>
                <a 
                    href="#kontak" 
                    on:click={closeMobileMenu}
                    class="font-medium text-gray-600 hover:text-indigo-500 transition-colors py-2 px-3 rounded-lg hover:bg-indigo-50"
                >
                    Kontak
                </a>
                <a 
                    href="#produk" 
                    on:click={closeMobileMenu}
                    class="bg-indigo-500 text-white font-semibold px-5 py-3 rounded-lg hover:bg-indigo-600 transition-shadow shadow-lg shadow-indigo-500/20 text-center mt-2"
                >
                    Pesan Sekarang
                </a>
            </nav>
        </div>
    {/if}
</header>