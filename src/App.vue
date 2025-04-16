<script setup>
// Importing necessary components for the Home page
import HelloWorld from './components/HelloWorld.vue';

const products = [
  {
    id: 1,
    name: 'Stainless Steel Tumbler',
    description: 'Tumbler ini terbuat dari bahan stainless steel berkualitas tinggi, tahan panas dan dingin. Biasanya dilengkapi dengan dinding ganda (double wall insulation) untuk menjaga suhu minuman lebih lama.',
    image: new URL('./assets/1.jpg', import.meta.url).href,
  },
  {
    id: 2,
    name: 'Custom Print Tumbler',
    description: 'Tumbler dengan desain cetak khusus, bisa berupa gambar bunga, nama pribadi, logo brand, atau ilustrasi favorit. Biasanya berbahan plastik BPA-free atau stainless ringan.',
    image: new URL('./assets/2.jpg', import.meta.url).href,
  },
  {
    id: 3,
    name: 'Tuumbler Lipat',
    description: 'Tumbler lipat ini berbahan silikon food-grade dan bisa dilipat saat tidak digunakan. Cocok untuk aktivitas outdoor atau yang butuh hemat ruang.',
    image: new URL('./assets/3.jpg', import.meta.url).href,
  },
  {
    id: 4,
    name: 'Tumbler Warna',
    description: 'Tumbler yang dapat berubah warna tergantung suhu minuman di dalamnya atau terkena cahaya. Biasanya dibuat dari plastik khusus dengan teknologi termokromik.',
    image: new URL('./assets/4.jpg', import.meta.url).href,
  },
];
</script>

<template>
  <div class="home">
    <header>
      <img alt="Vue logo" class="logo" src="@/assets/a.jpg" width="125" height="125" />
      <h1>Welcome to GLUP Marketplace</h1>
    </header>

    <section class="marketplace">
      <main>
        <div class="product-cards">
          <div class="card" v-for="product in products" :key="product.id">
            <img :src="product.image" :alt="product.name" class="product-image" />
            <h2 class="product-name">{{ product.name }}</h2>
            <p class="product-description">{{ product.description }}</p>
          </div>
        </div>
      </main>
    </section>

    <footer>
      <p>&copy; 2025 Marketplace GLUP. All rights reserved.</p>
    </footer>
  </div>
</template>

<style scoped>
.home {
  text-align: center;
  padding: 2rem;
}

header {
  background-color: #f2e5ce;
  padding: 1rem;
  border-bottom: 1px solid #ddd;
}

header h1 {
  margin: 0.5rem 0;
  font-size: 2rem;
  color: #333;
}

main {
  max-width: 100%;
  margin: 0;
}

.marketplace {
  text-align: center;
  padding: 2rem;
}

.product-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 2rem;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.product-image {
  width: 100%;
  height: auto;
  border-radius: 4px;
}

.product-name {
  font-size: 1.25rem;
  margin: 0.5rem 0;
  color: #333;
}

.product-description {
  font-size: 0.875rem;
  color: #666;
}

footer {
  background-color: #f5f5f5;
  padding: 1rem;
  border-top: 1px solid #ddd;
  font-size: 0.875rem;
  color: #666;
}

@media (max-width: 768px) {
  .product-cards {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 2rem;
  }

  .card {
    padding: 2rem;
  }

  .product-name {
    font-size: 1rem;
  }

  .product-description {
    font-size: 0.75rem;
  }
}

@media (max-width: 480px) {
  .product-cards {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .card {
    padding: 2rem;
  }

  .product-name {
    font-size: 0.875rem;
  }

  .product-description {
    font-size: 0.75rem;
  }

  header h1 {
    font-size: 1.5rem;
  }

  .logo {
    width: 100px;
    height: 100px;
  }

  .product-image {
    width: 80%;
    height: auto;
    margin: 0 auto;
  }
}
</style>
