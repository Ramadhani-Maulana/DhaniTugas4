<template>
  <h1>Ramadhani Maulana Raharjo - 233140701111025</h1>
  
  <!-- Button Counter -->
    <div id="app">
    <button @click="incrementCounter">Menambah Counter</button>
    <p>Counter: {{ counter }}</p>

    <!-- Image Carousel -->
    <div class="carousel-section">
      <p>
        <button @click="prevImage">Sebelum</button>
        <button @click="nextImage">Sesudah</button>
      </p>
        <img :src="images[currentImage]" class="carousel-image" />
    </div>

    <!-- Merubah Box Color -->
    <button @click="changeBodyBackground">Merubah Background</button>
  </div>
</template>

<script>
  export default {
    data() {
      return {

    // Untuk Klik Counter
    counter: 0,
    lastCounterValue: 0,

    // Saya Mengambil Gambar Pada Chrome
    images: [ 
      'https://memorandum.disway.id/uploads/29a8c63c-f6c5-4ab4-b29d-4dc72bdcb51b.jpg', 
      'https://img.okezone.com/content/2023/07/03/408/2840530/10-tempat-wisata-pantai-terpopuler-di-malang-2023-nomor-6-mirip-tanah-lot-bali-28tuO2uo6c.jpg',
      'https://ik.imagekit.io/tvlk/blog/2018/08/Malang-Pantai-Goa-Cina-1073730011.jpg?tr=dpr-2,w-675',
      'https://o-cdn-cas.sirclocdn.com/parenting/images/pantai-di-malang_ZuoFzE1.width-800.format-webp.webp',
      'https://c4.wallpaperflare.com/wallpaper/10/286/375/mount-bromo-wallpapers-hd-wallpaper-preview.jpg',
      'https://assets.promediateknologi.id/crop/107x171:1036x811/750x0/webp/photo/2023/03/16/Brakseng-1-2355817533.jpg',
      'https://media.istockphoto.com/id/591992956/id/foto/panorama-pemandangan-gunung-rinjani-indonesia.jpg?s=612x612&w=0&k=20&c=1DpsfAej_6Z3J689e_QVNbmDJYFvFAfjBqgEM7V04gk=',
      'https://thumb.viva.id/vivawisata/1265x711/2023/06/27/649a814523b88-fakultas-kedokteran-ub_wisata.jpg',
      'https://c4.wallpaperflare.com/wallpaper/974/265/195/nature-2560x1440-greenery-houses-wallpaper-preview.jpg',
      'https://w0.peakpx.com/wallpaper/147/494/HD-wallpaper-switzerland-ultra-swiss.jpg',
      'https://w0.peakpx.com/wallpaper/976/702/HD-wallpaper-switzerland-summer-beautiful-nature-mountains-alps-swiss-nature.jpg'
      ],
    currentImage: 0
  };
},

methods: {
  // Method Untuk click counter
  incrementCounter() {
    this.lastCounterValue = this.counter;
    this.counter++;
  },

  // Method Untuk color changer
  changeBodyBackground() {
    const randomColor = '#' + Math.floor(Math.random() * 16777215).toString(18);
    document.body.style.backgroundColor = randomColor;
  },

  // Methods Untuk Image Carousel
  prevImage() {
    if (this.currentImage > 0) {
      this.currentImage--;
    } else {
      this.currentImage = this.images.length - 1;
    }
  },

  nextImage() {
      if (this.currentImage < this.images.length - 1) {
        this.currentImage++;
      } else {
        this.currentImage = 0;
      }
    }
  }
};
</script>

<style>
  #app {
    text-align: center;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    height: 120vh;
    width: 120vw;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    position: relative;
  }

  div > div {
    transition: background-color 0.1s ease;
  }

  button {
    padding: 0.4rem 2rem;
    font-size: 1.7rem;
    cursor: pointer;
  }

  .color-changer-section {
    width: 100vw;
    height: 100vh;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .carousel-section {
    margin-top: 40px;
  }

  .carousel-image {
    width: 800px;
    height: 550px;
    margin: 30px 0;
    border: 4px solid #ffffff; 
    border-radius: 1px; 
  }
</style>
