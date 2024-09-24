<template>
  <div id="app">
    <header>
      <h1>Profile Page</h1>
    </header>
    
    <!-- Profile Section -->
    <div class="profile-page">
      <div class="profile-card">
        <img src="/images/ProfilPage.jpeg" alt="Profile Picture" class="profile-image" />
        <h1>{{ fullName }}</h1>
        <p>{{ bio }}</p>
      </div>
    </div>

    <!-- Links Section (Scrollable) -->
    <section class="social-section">
      <div class="card-grid">
        <div class="card" v-for="(social, index) in socials" :key="index">
          <h2>{{ social.name }}</h2>
          <p>{{ social.description }}</p>
          <a :href="social.link" target="_blank" class="social-link">Click</a>
        </div>
      </div>
    </section>

    <!-- Image Carousel Section -->
    <section class="carousel-section">
      <h2>My Gallery</h2>
      <div class="carousel-container">
        <div class="carousel-track">
          <div class="carousel-item" v-for="(image, index) in images" :key="index">
            <img :src="image.src" :alt="image.alt" class="carousel-image" />
            <button class="carousel-button">Gambar {{ index + 1 }}</button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fullName: 'Adinda Putri Nurevani',
      profileImage: 'https://via.placeholder.com/150', // gambar
      bio: 'Saat kita sadar akan kerendahan hati, disaat itu pula kesombongan akan',
      socials: [
        {
          name: "Instagram",
          description: "Follow my Instagram account.",
          link: "https://www.instagram.com/adindaputrn_?igsh=MWN5MHQ0NXBmcml3Mg=="
        },
        {
          name: "TikTok",
          description: "Check out my TikTok videos.",
          link: "https://www.tiktok.com/@adindaputrn?_t=8pyzzvjdcDB&_r=1"
        },
        {
          name: "LinkedIn",
          description: "Connect with me on LinkedIn.",
          link: "https://www.linkedin.com/in/adinda-putri-nurevani-bb0367289?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app"
        },
        {
          name: "Shopee",
          description: "Visit my Shopee store.",
          link: "https://shpe.site/adindaputrin"
        },
        {
          name: "University",
          description: "  .",
          link: "https://www.instagram.com/univ.brawijaya?igsh=M3Nlb3BuYmM2cGUw"
        },
        {
          name: "SMA",
          description: "Information about my high school.",
          link: "https://www.instagram.com/oskasmablu?igsh=amE5cGFheG0zNGs2"
        },
        {
          name: "SMP",
          description: "Information about my middle school.",
          link: "https://www.instagram.com/smpnegeri1sukoramee?igsh=ZXBpMmEwaHFkdjR0"
        },
        {
          name: "SD",
          description: "Information about my elementary school.",
          link: "https://maps.app.goo.gl/jseD17irmNNYcSDq6"
        }
      ],
      images: [
        { src: '/images/sma.jpeg', alt: 'Image 1' },
        { src: '/images/kuliah.jpeg', alt: 'Image 2' },
        { src: '/images/pramuka.jpeg', alt: 'Image 3' },
        { src: '/images/pmr.jpeg', alt: 'Image 4' }
      ]
    };
  },
};
</script>


<style scoped>

.nuxt {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Times New Roman', Times, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  overflow-y: auto;
}

header {
  background-color: pink;
  padding: 20px;
  color: white;
  text-align: center;
}

.profile-page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: calc(100vh - 100px); /* Kurangi tinggi header */
  background-color: rgb(245, 152, 183);
  padding: 20px 0;
}

.profile-card {
  background: pink;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 300px;
}

.profile-image {
  border-radius: 50%;
  width: 150px;
  height: 150px;
  object-fit: cover;
  margin-bottom: 20px;
}
.carousel-container {
  overflow-x: auto;
  display: flex;
  justify-content: center;
  scrollbar-width: none; /* Hide scrollbar in Firefox */
}

.carousel-container::-webkit-scrollbar {
  display: none; /* Hide scrollbar in Chrome/Safari */
}

.carousel-track {
  display: flex;
  gap: 20px;
}

.carousel-item {
  background-color: #fff;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 200px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.carousel-image {
  width: 150px;
  height: 150px;
  border-radius: 10px;
  object-fit: cover;
  margin-bottom: 10px;
}

.carousel-button {
  padding: 10px;
  background-color: #42b983;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.carousel-button:hover {
  background-color: #358c70;
}

h1 {
  font-size: 24px;
  margin-bottom: 5px;
}

.social-section {
  padding: 40px 0;
  background-color: pink;
  display: flex;
  justify-content: center;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  justify-items: center;
  width: 100%;
  max-width: 1000px;
}

.card {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  width: 200px;
  text-align: center;
}

.social-link {
  display: inline-block;
  margin-top: 10px;
  padding: 10px 20px;
  background-color: #42b983;
  color: white;
  border-radius: 5px;
  text-decoration: none;
}

.social-link:hover {
  background-color: #358c70;
}
</style>
