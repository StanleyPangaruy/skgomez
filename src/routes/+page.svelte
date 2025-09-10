<script lang="ts">
  // later you can fetch this dynamically
  const skOfTheMonth = {
    name: "Jane Marnel E. Cantillana",
    role: "SK Councilor",
    image: "https://via.placeholder.com/300x300.png?text=SK+of+the+Month",
    quote: "I'm just a baby. I'm just a girl."
  };
</script>

<!-- Hero Section -->
<section class="bg-green-600 text-white py-20">
  <div class="max-w-7xl mx-auto px-6 text-center">
    <h1 class="text-4xl md:text-6xl font-extrabold mb-6">
      Sangguniang Kabataan ng Gomez
    </h1>
    <p class="text-lg md:text-xl mb-8 max-w-2xl mx-auto">
      Empowering the youth of Gomez to lead, serve, and create meaningful change
      in our community. ✨
    </p>
    <div class="flex justify-center gap-4">
      <a
        href="/programs"
        class="px-6 py-3 bg-white text-green-600 font-semibold rounded-lg shadow hover:bg-gray-100 transition"
      >
        Explore Programs
      </a>
      <a
        href="/services"
        class="px-6 py-3 bg-yellow-400 text-gray-900 font-semibold rounded-lg shadow hover:bg-yellow-300 transition"
      >
        Youth Services
      </a>
    </div>
  </div>
</section>

<!-- About Section -->
<section class="py-16 bg-gray-50">
  <div class="max-w-6xl mx-auto px-6 text-center">
    <h2 class="text-3xl font-bold text-gray-900 mb-8">
      Who We Are
    </h2>
    <p class="text-lg text-gray-600 max-w-3xl mx-auto">
      The Sangguniang Kabataan (SK) of Gomez is dedicated to promoting youth
      leadership, participation, and community involvement. We envision a
      future where the youth are empowered to take part in nation-building
      through education, sports, environment, and civic programs.
    </p>
  </div>
</section>

<!-- Programs Section -->
<section class="py-16 bg-white">
  <div class="max-w-7xl mx-auto px-6">
    <h2 class="text-3xl font-bold text-center text-gray-900 mb-12">
      Our Key Programs
    </h2>
    <div class="grid md:grid-cols-3 gap-10">
      <div class="bg-green-50 p-8 rounded-2xl shadow hover:shadow-lg transition">
        <h3 class="text-xl font-semibold text-green-700 mb-4">Education</h3>
        <p class="text-gray-600">
          Scholarships, tutorials, and study hubs to support young learners.
        </p>
      </div>
      <div class="bg-green-50 p-8 rounded-2xl shadow hover:shadow-lg transition">
        <h3 class="text-xl font-semibold text-green-700 mb-4">Sports & Health</h3>
        <p class="text-gray-600">
          Sports fests, fitness campaigns, and medical missions for active youth.
        </p>
      </div>
      <div class="bg-green-50 p-8 rounded-2xl shadow hover:shadow-lg transition">
        <h3 class="text-xl font-semibold text-green-700 mb-4">Environment</h3>
        <p class="text-gray-600">
          Tree planting, clean-up drives, and eco-awareness activities.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- SK of the Month Section -->
<section class="py-20 bg-gray-100">
  <div class="max-w-5xl mx-auto px-6 text-center">
    <h2 class="text-3xl font-bold text-gray-900 mb-12">
      🌟 SK of the Month
    </h2>
    <div class="bg-white rounded-2xl shadow-lg p-8 md:flex items-center text-left">
      <img
        src={skOfTheMonth.image}
        alt="SK of the Month"
        class="w-40 h-40 rounded-full mx-auto md:mx-0 md:mr-8 object-cover shadow-md"
      />
      <div>
        <h3 class="text-2xl font-bold text-green-700">{skOfTheMonth.name}</h3>
        <p class="text-sm text-gray-500 mb-4">{skOfTheMonth.role}</p>
        <blockquote class="italic text-gray-700 border-l-4 border-green-500 pl-4">
          “{skOfTheMonth.quote}”
        </blockquote>
      </div>
    </div>
  </div>
</section>

<!-- Call to Action -->
<section class="py-20 bg-green-700 text-white text-center">
  <div class="max-w-3xl mx-auto px-6">
    <h2 class="text-3xl md:text-4xl font-bold mb-6">
      Be part of the change 🌱
    </h2>
    <p class="mb-8 text-lg">
      Join us in shaping a brighter and more inclusive future for the youth of Gomez.
    </p>
    <a
      href="/reports"
      class="px-8 py-4 bg-yellow-400 text-gray-900 font-semibold rounded-lg shadow hover:bg-yellow-300 transition"
    >
      View Transparency Reports
    </a>
  </div>
</section>

<!-- Footer -->
<footer class="bg-gray-900 text-gray-400 py-8">
  <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center">
    <p>&copy; {new Date().getFullYear()} Sangguniang Kabataan ng Gomez. All rights reserved.</p>
    <div class="flex gap-6 mt-4 md:mt-0">
      <a href="https://www.facebook.com/sk.gomez.754084" class="hover:text-white">Facebook</a>
      <a href="https://www.instagram.com/skgomez2023/" class="hover:text-white">Instagram</a>
      <a href="https://www.tiktok.com/@sk.gomez.2023" class="hover:text-white">Tiktok</a>
    </div>
  </div>
</footer>
