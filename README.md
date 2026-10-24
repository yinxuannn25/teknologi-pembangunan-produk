<!DOCTYPE html>
<html lang="ms">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Misi Wira Sukan Kebanggaan Malaysia - 6 Zon Interaktif Penuh</title>
  <!-- Tailwind CSS & Lucide Icons -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest"></script>
  <!-- Google Fonts: Fredoka & Quicksand -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">
  <!-- Canvas Confetti -->
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

  <style>
    body {
      font-family: 'Quicksand', sans-serif;
      background-color: #0B1329;
      background-image: 
        radial-gradient(circle at 10% 15%, rgba(245, 158, 11, 0.15) 0%, transparent 35%),
        radial-gradient(circle at 90% 85%, rgba(239, 68, 68, 0.15) 0%, transparent 35%),
        radial-gradient(circle at 50% 50%, rgba(59, 130, 246, 0.1) 0%, transparent 40%);
    }
    h1, h2, h3, h4, .font-heading {
      font-family: 'Fredoka', cursive, sans-serif;
    }
    
    /* Animasi Gerakan Atlet Kartun */
    @keyframes smashAnim {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      30% { transform: translateY(-12px) rotate(-8deg); }
      70% { transform: translateY(4px) rotate(5deg); }
    }
    .anim-smash { animation: smashAnim 1.6s infinite ease-in-out; }

    @keyframes pedalAnim {
      0%, 100% { transform: translateX(0); }
      50% { transform: translateX(8px) scale(1.04); }
    }
    .anim-pedal { animation: pedalAnim 1.3s infinite ease-in-out; }

    @keyframes jumpAnim {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-16px) scale(1.06); }
    }
    .anim-jump { animation: jumpAnim 1.7s infinite ease-in-out; }

    .glow-gold { box-shadow: 0 0 25px rgba(245, 158, 11, 0.22); }
  </style>
</head>
<body class="min-h-screen text-slate-100 flex flex-col justify-between p-3 sm:p-6">

  <!-- Header Papan Skor Stadium -->
  <header class="max-w-5xl mx-auto w-full bg-slate-900/95 backdrop-blur-md rounded-3xl p-4 sm:p-5 border border-amber-500/30 flex flex-col sm:flex-row items-center justify-between gap-4 glow-gold">
    <div class="flex items-center gap-3">
      <div class="w-14 h-14 rounded-2xl bg-gradient-to-tr from-amber-400 via-orange-500 to-rose-600 flex items-center justify-center text-3xl shadow-lg shadow-amber-500/20">
        🐯
      </div>
      <div>
        <div class="flex items-center gap-2">
          <span class="bg-amber-500/20 text-amber-400 text-[11px] font-bold px-2.5 py-0.5 rounded-full font-heading uppercase tracking-wider border border-amber-500/30">
            Tajuk 12: Sejarah Tahun 6
          </span>
          <span class="bg-blue-500/20 text-blue-300 text-[11px] font-bold px-2 py-0.5 rounded-full font-heading border border-blue-500/30">
            6 Zon Pembelajaran Interaktif
          </span>
        </div>
        <h1 class="text-xl sm:text-2xl font-bold text-white font-heading">Misi Wira Sukan Kebanggaan Malaysia</h1>
      </div>
    </div>

    <!-- Papan Skor & Lencana -->
    <div class="flex items-center gap-3 bg-slate-800/90 px-4 py-2.5 rounded-2xl border border-slate-700">
      <div class="flex items-center gap-1.5 font-heading text-xs font-bold text-slate-300">
        <span class="text-amber-400">⭐ Skor Semangat:</span>
        <span id="player-score" class="text-lg text-amber-400 font-extrabold">0</span>
      </div>
      <div class="h-4 w-px bg-slate-700"></div>
      <div class="flex items-center gap-1.5" id="badge-container">
        <!-- 6 Lencana Interaktif -->
      </div>
    </div>
  </header>

  <!-- Pentas Utama Interaktif -->
  <main class="max-w-5xl mx-auto w-full flex-1 my-4 flex flex-col">

    <!-- 1. HUB UTAMA: PETA 6 ZON PEMBELAJARAN -->
    <div id="screen-hub" class="bg-slate-900/90 rounded-3xl p-6 sm:p-8 border border-slate-800 flex flex-col gap-6">
      
      <!-- Pengenalan Maskot Rimau Wira -->
      <div class="flex flex-col sm:flex-row items-center gap-6 bg-gradient-to-r from-amber-950/40 via-slate-800/80 to-blue-950/40 p-6 rounded-3xl border border-amber-500/20">
        <div class="w-24 h-24 rounded-3xl bg-slate-800 flex items-center justify-center text-6xl border-2 border-amber-400 shrink-0 shadow-inner">
          🐯
        </div>
        <div>
          <h2 class="text-xl sm:text-2xl font-bold text-amber-400 font-heading">Setiap Zon Kini Dilengkapi Aktiviti Interaktif Penuh!</h2>
          <p class="text-sm text-slate-300 mt-1 leading-relaxed">
            Terokai garis masa persatuan, seret trofi kejohanan, uji meter rekod legenda sukan & paralimpik, susun padang perpaduan, dan buat keputusan di bilik rundingan keharmonian!
          </p>
          <div class="mt-3 flex items-center gap-2 text-xs font-bold text-amber-300">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span> 
            Kemajuan Semasa: <span id="progress-text" class="text-emerald-400 font-bold">0 / 6 Zon Selesai</span>
          </div>
        </div>
      </div>

      <!-- Grid 3 Kluster Standard Pembelajaran -->
      <div class="space-y-6">

        <!-- KLUSTER 1: SP 12.1.2 (Pencapaian & Persatuan Sukan) -->
        <div class="bg-slate-800/40 p-5 rounded-3xl border border-slate-700/80">
          <div class="flex items-center justify-between mb-3">
            <div class="flex items-center gap-2">
              <span class="px-3 py-1 bg-amber-500/20 text-amber-300 text-xs font-bold rounded-full border border-amber-400/30 font-heading">SP 12.1.2</span>
              <h3 class="text-base sm:text-lg font-bold text-white font-heading">Persatuan & Kejayaan Kebangsaan (M/S 144-145)</h3>
            </div>
            <span class="text-xs text-slate-400 font-semibold">BAM • FAM • KOM • MHC</span>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- Zon 1 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-amber-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">🏸⚽</span>
                  <span id="badge-tag-1" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 1</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 1: Garis Masa & Aksi Persatuan</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Susun tahun penubuhan (1952-1963) dan aktifkan aksi kartun sukan.</p>
              </div>
              <button onclick="launchZone(1)" class="mt-4 w-full bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 1
              </button>
            </div>
            <!-- Zon 2 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-amber-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">🏆✨</span>
                  <span id="badge-tag-2" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 2</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 2: Penyerahan Trofi Kejohanan</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Padankan trofi dunia (Piala Thomas, Olimpik, Sukan Asia) ke peti persatuan.</p>
              </div>
              <button onclick="launchZone(2)" class="mt-4 w-full bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 2
              </button>
            </div>
          </div>
        </div>

        <!-- KLUSTER 2: SP 12.1.4 (Tokoh Inspirasi & Paralimpik) -->
        <div class="bg-slate-800/40 p-5 rounded-3xl border border-slate-700/80">
          <div class="flex items-center justify-between mb-3">
            <div class="flex items-center gap-2">
              <span class="px-3 py-1 bg-blue-500/20 text-blue-300 text-xs font-bold rounded-full border border-blue-400/30 font-heading">SP 12.1.4</span>
              <h3 class="text-base sm:text-lg font-bold text-white font-heading">Tokoh Sukan & Wira Paralimpik (M/S 146-148)</h3>
            </div>
            <span class="text-xs text-slate-400 font-semibold">Legenda & "Kami Luar Biasa"</span>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- Zon 3 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-blue-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">🥇🚴‍♂️</span>
                  <span id="badge-tag-3" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 3</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 3: Pengimbas Tolok Rekod Legenda</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Imbas kad tokoh dan putar tolok rekod 108 bulan Nicol David & 22 emas Sukan SEA.</p>
              </div>
              <button onclick="launchZone(3)" class="mt-4 w-full bg-blue-500 hover:bg-blue-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 3
              </button>
            </div>
            <!-- Zon 4 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-blue-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">⏱️🎯</span>
                  <span id="badge-tag-4" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 4</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 4: Pengukur Rekod Dunia Paralimpik</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Laras pita pengukur maya bagi lompatan 7.60m Latif Romly & lontaran 16.84m Ziyad.</p>
              </div>
              <button onclick="launchZone(4)" class="mt-4 w-full bg-blue-500 hover:bg-blue-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 4
              </button>
            </div>
          </div>
        </div>

        <!-- KLUSTER 3: SP 12.1.1 (Perpaduan & Keharmonian Kaum) -->
        <div class="bg-slate-800/40 p-5 rounded-3xl border border-slate-700/80">
          <div class="flex items-center justify-between mb-3">
            <div class="flex items-center gap-2">
              <span class="px-3 py-1 bg-emerald-500/20 text-emerald-300 text-xs font-bold rounded-full border border-emerald-400/30 font-heading">SP 12.1.1</span>
              <h3 class="text-base sm:text-lg font-bold text-white font-heading">Sukan Alat Perpaduan & Keharmonian (M/S 149)</h3>
            </div>
            <span class="text-xs text-slate-400 font-semibold">RIMUP • 1M1S • MSSM</span>
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <!-- Zon 5 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-emerald-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">🏫🤝</span>
                  <span id="badge-tag-5" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 5</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 5: Pengatur Padang Harmoni Sekolah</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Tempatkan RIMUP (2005) & 1M1S (2011) ke padang untuk menyalakan Obor Muhibah.</p>
              </div>
              <button onclick="launchZone(5)" class="mt-4 w-full bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 5
              </button>
            </div>
            <!-- Zon 6 -->
            <div class="bg-slate-800/90 p-4 rounded-2xl border border-slate-700 hover:border-emerald-400 transition-all flex flex-col justify-between">
              <div>
                <div class="flex items-center justify-between mb-2">
                  <span class="text-2xl">⚖️❤️</span>
                  <span id="badge-tag-6" class="text-[10px] bg-slate-700 text-slate-300 px-2 py-0.5 rounded-full font-bold">Zon 6</span>
                </div>
                <h4 class="text-sm font-bold text-white font-heading">Zon 6: Bilik Rundingan Ejen Perpaduan</h4>
                <p class="text-xs text-slate-400 mt-1">Interaktif: Selesaikan konflik emosi pemain pelbagai kaum & capai 100% Meter Keharmonian.</p>
              </div>
              <button onclick="launchZone(6)" class="mt-4 w-full bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold py-2 rounded-xl text-xs font-heading flex items-center justify-center gap-1.5 transition">
                <i data-lucide="play" class="w-3.5 h-3.5"></i> Mula Interaktif Zon 6
              </button>
            </div>
          </div>
        </div>

      </div>

      <!-- Kad Buka Sijil Tamat -->
      <div id="hub-cert-card" class="hidden bg-gradient-to-r from-amber-500 via-orange-500 to-rose-600 rounded-2xl p-5 text-slate-950 flex flex-col sm:flex-row items-center justify-between gap-4 shadow-xl">
        <div class="flex items-center gap-3">
          <span class="text-4xl">🎓</span>
          <div>
            <h4 class="font-bold font-heading text-lg text-slate-950">Syabas! Kesemua 6 Zon Interaktif Lengkap!</h4>
            <p class="text-xs font-semibold text-slate-900">Anda kini layak menerima pentauliahan rasmi Duta Sukan Negara.</p>
          </div>
        </div>
        <button onclick="openCertificateScreen()" class="bg-slate-950 hover:bg-slate-900 text-amber-400 font-bold px-6 py-2.5 rounded-xl shadow font-heading text-sm transition">
          Buka Sijil Pentauliahan
        </button>
      </div>

    </div>

    <!-- 2. KONTENA ZON INTERAKTIF DINAMIK -->
    <div id="screen-zone" class="hidden bg-slate-900/90 rounded-3xl p-6 sm:p-8 border border-slate-800 flex-1 flex flex-col justify-between">
      <div id="zone-content-area"></div>
    </div>

    <!-- 3. SKRIN SIJIL PENTAULIAHAN DIGITAL -->
    <div id="screen-certificate" class="hidden bg-slate-900 rounded-3xl p-6 sm:p-10 border-4 border-amber-400 flex flex-col items-center text-center relative overflow-hidden glow-gold">
      <div class="w-20 h-20 rounded-2xl bg-amber-400/20 border-2 border-amber-400 flex items-center justify-center text-5xl mb-4">
        🎖️
      </div>

      <span class="bg-amber-400/20 text-amber-400 text-xs font-bold font-heading px-4 py-1 rounded-full uppercase tracking-widest border border-amber-400/30">
        Kementerian Pendidikan Malaysia • Sejarah Tahun 6
      </span>
      <h2 class="text-2xl sm:text-3xl font-extrabold text-white font-heading mt-2">
        SIJIL PENTAULIAHAN DUTA SUKAN NEGARA
      </h2>
      <p class="text-xs sm:text-sm text-slate-400 max-w-lg mt-1 font-medium">
        Diperakui bahawa murid ini telah menamatkan kesemua 6 zon pembelajaran interaktif bagi topik Sukan Kebanggaan Negara dengan jayanya.
      </p>

      <div class="my-6 bg-slate-800/80 border-2 border-dashed border-amber-400/60 rounded-2xl p-4 w-full max-w-md space-y-3">
        <div>
          <label class="text-[10px] font-bold text-amber-300 uppercase tracking-wider block">Nama Murid:</label>
          <input type="text" id="cert-student-name" value="Wira Sejarah Cilik" class="text-center font-heading text-lg font-bold text-white bg-transparent w-full focus:outline-hidden border-b border-amber-400 pb-0.5">
        </div>
        <div>
          <label class="text-[10px] font-bold text-amber-300 uppercase tracking-wider block">Sekolah:</label>
          <input type="text" id="cert-school-name" value="Sekolah Kebangsaan Malaysia" class="text-center text-xs font-semibold text-slate-300 bg-transparent w-full focus:outline-hidden border-b border-slate-600 pb-0.5">
        </div>
      </div>

      <div class="grid grid-cols-6 gap-2 max-w-md w-full mb-6 text-center">
        <div class="bg-slate-800 p-2 rounded-xl border border-amber-500/30"><span class="text-xl">🏸</span><p class="text-[8px] text-amber-300 mt-1">Zon 1</p></div>
        <div class="bg-slate-800 p-2 rounded-xl border border-amber-500/30"><span class="text-xl">🏆</span><p class="text-[8px] text-amber-300 mt-1">Zon 2</p></div>
        <div class="bg-slate-800 p-2 rounded-xl border border-blue-500/30"><span class="text-xl">🥇</span><p class="text-[8px] text-blue-300 mt-1">Zon 3</p></div>
        <div class="bg-slate-800 p-2 rounded-xl border border-blue-500/30"><span class="text-xl">⏱️</span><p class="text-[8px] text-blue-300 mt-1">Zon 4</p></div>
        <div class="bg-slate-800 p-2 rounded-xl border border-emerald-500/30"><span class="text-xl">🏫</span><p class="text-[8px] text-emerald-300 mt-1">Zon 5</p></div>
        <div class="bg-slate-800 p-2 rounded-xl border border-emerald-500/30"><span class="text-xl">🤝</span><p class="text-[8px] text-emerald-300 mt-1">Zon 6</p></div>
      </div>

      <div class="flex items-center justify-between w-full max-w-md pt-4 border-t border-slate-800 text-left">
        <div>
          <span class="text-[10px] text-slate-500 block font-bold">Tarikh:</span>
          <span id="cert-date" class="text-xs font-bold text-slate-300">11 Oktober 2026</span>
        </div>
        <div class="text-right">
          <span class="text-xs text-amber-400 font-heading font-bold">🐯 Rimau Wira</span>
          <span class="text-[10px] text-slate-500 block">Pusat Sukan Kebangsaan</span>
        </div>
      </div>

      <div class="mt-8 flex gap-3">
        <button onclick="window.print()" class="bg-amber-400 hover:bg-amber-300 text-slate-950 font-bold px-5 py-2.5 rounded-xl font-heading text-sm flex items-center gap-2 transition">
          <i data-lucide="printer" class="w-4 h-4"></i> Cetak Sijil
        </button>
        <button onclick="returnToHub()" class="bg-slate-800 hover:bg-slate-700 text-white font-bold px-5 py-2.5 rounded-xl font-heading text-sm flex items-center gap-2 transition">
          <i data-lucide="home" class="w-4 h-4"></i> Menu Utama
        </button>
      </div>
    </div>

  </main>

  <!-- Web Audio API Synthesizer Ringan -->
  <script>
    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    function playSfx(type) {
      try {
        if (audioCtx.state === 'suspended') audioCtx.resume();
        const now = audioCtx.currentTime;
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        osc.connect(gain);
        gain.connect(audioCtx.destination);

        if (type === 'click') {
          osc.frequency.setValueAtTime(420, now);
          osc.frequency.exponentialRampToValueAtTime(750, now + 0.08);
          gain.gain.setValueAtTime(0.1, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.08);
          osc.start(now);
          osc.stop(now + 0.08);
        } else if (type === 'action') {
          osc.frequency.setValueAtTime(320, now);
          osc.frequency.exponentialRampToValueAtTime(640, now + 0.12);
          gain.gain.setValueAtTime(0.12, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.12);
          osc.start(now);
          osc.stop(now + 0.12);
        } else if (type === 'correct') {
          osc.frequency.setValueAtTime(523.25, now);
          osc.frequency.setValueAtTime(659.25, now + 0.08);
          osc.frequency.setValueAtTime(783.99, now + 0.16);
          gain.gain.setValueAtTime(0.18, now);
          gain.gain.exponentialRampToValueAtTime(0.01, now + 0.32);
          osc.start(now);
          osc.stop(now + 0.32);
        } else if (type === 'fanfare') {
          [523, 659, 783, 1046].forEach((f, i) => {
            const o = audioCtx.createOscillator();
            const g = audioCtx.createGain();
            o.connect(g);
            g.connect(audioCtx.destination);
            o.frequency.value = f;
            g.gain.setValueAtTime(0.12, now + i * 0.09);
            g.gain.exponentialRampToValueAtTime(0.001, now + i * 0.09 + 0.25);
            o.start(now + i * 0.09);
            o.stop(now + i * 0.09 + 0.25);
          });
        }
      } catch (e) {}
    }
  </script>

  <!-- Enjin Logik 6 Zon Pembelajaran Interaktif Penuh -->
  <script>
    let currentScore = 0;
    let completedZones = new Set();
    let currentActiveZone = 1;

    function initBadges() {
      const container = document.getElementById('badge-container');
      container.innerHTML = '';
      const icons = ['🏸', '🏆', '🥇', '⏱️', '🏫', '🤝'];
      for (let i = 1; i <= 6; i++) {
        const isDone = completedZones.has(i);
        const span = document.createElement('span');
        span.id = `badge-${i}`;
        span.className = `w-7 h-7 rounded-lg flex items-center justify-center text-xs transition-all ${
          isDone ? 'bg-amber-400 text-slate-950 font-bold shadow' : 'bg-slate-700/60 opacity-30 grayscale'
        }`;
        span.textContent = icons[i - 1];
        container.appendChild(span);
      }
      document.getElementById('progress-text').textContent = `${completedZones.size} / 6 Zon Selesai`;
      if (completedZones.size === 6) {
        document.getElementById('hub-cert-card').classList.remove('hidden');
      }
    }

    function returnToHub() {
      playSfx('click');
      document.getElementById('screen-zone').classList.add('hidden');
      document.getElementById('screen-certificate').classList.add('hidden');
      document.getElementById('screen-hub').classList.remove('hidden');
      initBadges();
      lucide.createIcons();
    }

    function launchZone(zoneNum) {
      playSfx('click');
      currentActiveZone = zoneNum;
      document.getElementById('screen-hub').classList.add('hidden');
      document.getElementById('screen-zone').classList.remove('hidden');

      if (zoneNum === 1) renderZone1Interactive();
      else if (zoneNum === 2) renderZone2Interactive();
      else if (zoneNum === 3) renderZone3Interactive();
      else if (zoneNum === 4) renderZone4Interactive();
      else if (zoneNum === 5) renderZone5Interactive();
      else if (zoneNum === 6) renderZone6Interactive();
    }

    // ========================================================
    // ZON 1: GARIS MASA & PADANAN AKSI PERSATUAN (SP 12.1.2)
    // ========================================================
    let z1SelectedYear = null;
    const z1Timeline = [
      { year: "1952", code: "KOM", name: "Kesatuan Olahraga Malaysia (dahulu KOAM)", icon: "🏃‍♂️", anim: "anim-pedal", fact: "Melahirkan jaguh pecut Dr. M. Jegathesan & Rabuan Pit (Emas 100m Sukan Asia 1966 & 1982)!" },
      { year: "1953", code: "MHC", name: "Konfederasi Hoki Malaysia", icon: "🏑", anim: "anim-smash", fact: "Menganjurkan Liga Hoki Kebangsaan & skuad negara menduduki tempat ke-4 Piala Dunia 1975!" },
      { year: "1960", code: "BAM", name: "Persatuan Badminton Malaysia", icon: "🏸", anim: "anim-smash", fact: "Melahirkan Punch Gunalan, Misbun Sidek & Lee Chong Wei serta menjuarai 5 kali Piala Thomas!" },
      { year: "1963", code: "FAM", name: "Persatuan Bola Sepak Malaysia", icon: "⚽", anim: "anim-jump", fact: "Menganjurkan Liga Malaysia & skuad negara layak ke Sukan Olimpik Munich 1972 & Moscow 1980!" }
    ];

    function renderZone1Interactive() {
      const area = document.getElementById('zone-content-area');
      const active = z1Timeline.find(t => t.year === z1SelectedYear) || z1Timeline[0];

      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-amber-400/20 text-amber-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-amber-400/30">
              SP 12.1.2 • ZON 1: GARIS MASA PERSATUAN SUKAN
            </span>
            <button onclick="returnToHub()" class="text-xs font-bold text-slate-400 hover:text-rose-400 font-heading">Menu Utama</button>
          </div>

          <p class="text-xs text-slate-300 mb-3">Klik butang tahun penubuhan di garis masa untuk mengaktifkan aksi kartun atlet dan mengkaji fakta penubuhannya:</p>

          <!-- Bar Garis Masa Interaktif -->
          <div class="grid grid-cols-4 gap-2 mb-6">
            ${z1Timeline.map(t => `
              <button onclick="z1PickYear('${t.year}')" class="p-3 rounded-2xl border-2 transition-all font-heading text-center ${
                active.year === t.year ? 'bg-amber-500 text-slate-950 border-amber-300 scale-102 shadow-lg' : 'bg-slate-800 text-slate-300 border-slate-700 hover:border-slate-500'
              }">
                <span class="block text-xs sm:text-sm font-extrabold">${t.year}</span>
                <span class="text-[11px] font-bold opacity-90">${t.code}</span>
              </button>
            `).join('')}
          </div>

          <!-- Pentas Animasi Aksi Sukan -->
          <div class="flex flex-col sm:flex-row items-center justify-center gap-6 bg-slate-800/60 p-6 rounded-3xl border border-slate-700">
            <div onclick="playSfx('action'); confetti({particleCount: 25, spread: 50});" class="p-6 bg-slate-900 rounded-2xl border-2 border-amber-400/50 cursor-pointer text-center group hover:scale-105 transition-all shadow-inner">
              <span class="text-6xl inline-block ${active.anim}">${active.icon}</span>
              <p class="text-[10px] text-amber-300 font-bold mt-2 uppercase font-heading">Sentuh Aksi!</p>
            </div>
            <div class="max-w-md">
              <span class="text-xs text-amber-400 font-bold font-heading uppercase">Tahun Penubuhan: ${active.year}</span>
              <h3 class="text-xl font-bold text-white font-heading mt-0.5">${active.name} (${active.code})</h3>
              <p class="text-xs sm:text-sm text-slate-300 mt-2 leading-relaxed bg-slate-900/70 p-3 rounded-xl border border-slate-700">
                ${active.fact}
              </p>
            </div>
          </div>

          <div class="mt-6 pt-4 border-t border-slate-800 flex justify-end">
            <button onclick="completeZone(1)" class="bg-amber-500 hover:bg-amber-400 text-slate-950 px-6 py-2.5 rounded-xl text-xs font-bold font-heading shadow transition">
              Tuntut Lencana Zon 1 ✓
            </button>
          </div>
        </div>
      `;
      lucide.createIcons();
    }

    function z1PickYear(yr) {
      playSfx('click');
      z1SelectedYear = yr;
      renderZone1Interactive();
    }

    // ========================================================
    // ZON 2: CABARAN PENYERAHAN TROFI KEJOHANAN (SP 12.1.2)
    // ========================================================
    let z2TrophyIdx = 0;
    const z2Trophies = [
      { trophy: "🏆 Piala Thomas (5 Kali Juara)", target: "BAM", clue: "Kejohanan badminton berpasukan lelaki paling berprestij di dunia." },
      { trophy: "🎫 Tiket Olimpik Munich 1972 & Moscow 1980", target: "FAM", clue: "Skuad bola sepak kebangsaan layak ke temasya sukan terbesar dunia." },
      { trophy: "🥇 Pingat Emas 100m Sukan Asia 1966 & 1982", target: "KOM", clue: "Kejayaan manis jaguh pecut olahraga negara di pentas Asia." },
      { trophy: "🎖️ Tempat Ke-4 Piala Dunia 1975", target: "MHC", clue: "Pencapaian bersejarah pasukan hoki negara di Kuala Lumpur." }
    ];

    function renderZone2Interactive() {
      const area = document.getElementById('zone-content-area');
      const item = z2Trophies[z2TrophyIdx];

      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-amber-400/20 text-amber-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-amber-400/30">
              SP 12.1.2 • ZON 2: SIMULASI PENYERAHAN TROFI KEJOHANAN
            </span>
            <span class="text-xs font-bold text-slate-400">Piala ${z2TrophyIdx + 1} / ${z2Trophies.length}</span>
          </div>

          <!-- Peti Trofi Semasa -->
          <div class="bg-slate-800/80 p-5 rounded-3xl border-2 border-amber-400/50 mb-6 text-center">
            <span class="text-4xl inline-block mb-1">🎁</span>
            <h3 class="text-lg font-bold text-white font-heading">${item.trophy}</h3>
            <p class="text-xs text-slate-300 mt-1">${item.clue}</p>
          </div>

          <p class="text-xs text-center text-amber-300 font-bold mb-3 uppercase tracking-wider">Serahkan trofi ini kepada persatuan sukan yang betul:</p>

          <div class="grid grid-cols-2 sm:grid-cols-4 gap-3" id="z2-boxes">
            ${['BAM', 'FAM', 'KOM', 'MHC'].map(code => `
              <button onclick="z2DropTrophy('${code}')" class="p-4 bg-slate-800 hover:bg-slate-700 border-2 border-slate-700 hover:border-amber-400 rounded-2xl text-center font-heading transition">
                <span class="text-xl block mb-1">📦</span>
                <span class="text-sm font-bold text-white">${code}</span>
              </button>
            `).join('')}
          </div>

          <div id="z2-feedback" class="mt-4 hidden p-4 rounded-2xl text-xs sm:text-sm"></div>
        </div>
      `;
      lucide.createIcons();
    }

    function z2DropTrophy(chosen) {
      const item = z2Trophies[z2TrophyIdx];
      const fb = document.getElementById('z2-feedback');
      fb.classList.remove('hidden');

      if (chosen === item.target) {
        playSfx('correct');
        fb.className = "mt-4 p-4 rounded-2xl bg-emerald-950/70 border border-emerald-400 text-emerald-200";
        fb.innerHTML = `
          <strong>Tepat Sekali!</strong> ${item.trophy} diserahkan dengan betul ke arkib <strong>${item.target}</strong>.
          <button onclick="z2NextTrophy()" class="mt-3 block bg-emerald-400 text-slate-950 font-bold px-4 py-1.5 rounded-xl text-xs font-heading">Piala Seterusnya <i data-lucide="arrow-right" class="w-3.5 h-3.5 inline"></i></button>
        `;
      } else {
        playSfx('click');
        fb.className = "mt-4 p-4 rounded-2xl bg-rose-950/70 border border-rose-400 text-rose-200";
        fb.innerHTML = `Kurang tepat. Trofi ini bukan milik arkib ${chosen}. Sila rujuk petunjuk dan cuba lagi!`;
      }
      lucide.createIcons();
    }

    function z2NextTrophy() {
      z2TrophyIdx++;
      if (z2TrophyIdx < z2Trophies.length) {
        renderZone2Interactive();
      } else {
        completeZone(2);
      }
    }

    // ========================================================
    // ZON 3: PENGIMBAS TOLOK REKOD LEGENDA (SP 12.1.4)
    // ========================================================
    let z3ActiveIndex = 0;
    const z3Legends = [
      {
        nama: "Datuk Nicol Ann David",
        gelaran: "Ratu Skuasy Dunia",
        ikon: "🎾👑",
        meterLabel: "Tempoh Pemegang No. 1 Dunia",
        meterVal: "108 Bulan",
        meterPercent: "100%",
        fakta: "Menjuarai Kejohanan Terbuka Dunia sebanyak 8 kali dan dinobatkan Atlet Terunggul Sepanjang Zaman Sukan Dunia 2021!"
      },
      {
        nama: "Nurul Huda Abdullah @ Ch'ng Shu Lin",
        gelaran: "Ratu Renang Asia Tenggara",
        ikon: "🏊‍♀️🏅",
        meterLabel: "Kutipan Emas Sukan SEA",
        meterVal: "22 Pingat Emas",
        meterPercent: "90%",
        fakta: "Memecah rekod dengan meraih 7 emas (1985), 7 emas (1987), dan 8 emas (1989) dalam temasya Sukan SEA!"
      },
      {
        nama: "Dato' Mohd Azizulhasni Awang",
        gelaran: "The Pocket Rocketman",
        ikon: "🚴‍♂️🚀",
        meterLabel: "Pencapaian Olimpik & Dunia",
        meterVal: "Emas Dunia & 2 Pingat Olimpik",
        meterPercent: "95%",
        fakta: "Juara Keirin Dunia UCI 2017, meraih pingat gangsa di Olimpik Rio 2016 dan perak di Olimpik Tokyo 2020!"
      }
    ];

    function renderZone3Interactive() {
      const area = document.getElementById('zone-content-area');
      const cur = z3Legends[z3ActiveIndex];

      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-blue-400/20 text-blue-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-blue-400/30">
              SP 12.1.4 • ZON 3: PENGIMBAS TOLOK REKOD LEGENDA
            </span>
            <button onclick="returnToHub()" class="text-xs font-bold text-slate-400 hover:text-rose-400 font-heading">Menu Utama</button>
          </div>

          <!-- Pilihan Tab Pengimbas Tokoh -->
          <div class="grid grid-cols-3 gap-2 mb-6">
            ${z3Legends.map((leg, idx) => `
              <button onclick="z3PickLegend(${idx})" class="p-3 rounded-2xl border-2 font-heading transition text-center ${
                z3ActiveIndex === idx ? 'bg-blue-600 text-white border-blue-400 shadow-md' : 'bg-slate-800 text-slate-300 border-slate-700'
              }">
                <span class="text-lg block mb-0.5">${leg.ikon}</span>
                <span class="text-[11px] font-bold truncate block">${leg.nama.split(' ')[0]} ${leg.nama.split(' ')[1] || ''}</span>
              </button>
            `).join('')}
          </div>

          <!-- Pentas Tolok Rekod Interaktif -->
          <div class="bg-slate-800/60 p-6 rounded-3xl border border-slate-700 flex flex-col sm:flex-row items-center gap-6">
            <div onclick="playSfx('action'); confetti({particleCount: 20, spread: 40});" class="p-6 bg-slate-900 rounded-2xl border-2 border-blue-400/50 cursor-pointer text-center group hover:scale-105 transition-all shadow-inner">
              <span class="text-6xl inline-block anim-jump">${cur.ikon}</span>
              <p class="text-[10px] text-blue-300 font-bold mt-2 uppercase font-heading">Klik Tokoh!</p>
            </div>
            <div class="flex-1 w-full">
              <span class="text-xs text-blue-400 font-bold uppercase font-heading">${cur.gelaran}</span>
              <h3 class="text-xl font-bold text-white font-heading mt-0.5">${cur.nama}</h3>
              
              <!-- Tolok Visual Interaktif -->
              <div class="my-3 bg-slate-900 p-3 rounded-2xl border border-slate-700">
                <div class="flex justify-between text-xs font-bold text-slate-300 mb-1">
                  <span>${cur.meterLabel}</span>
                  <span class="text-amber-400 font-heading">${cur.meterVal}</span>
                </div>
                <div class="w-full h-3 bg-slate-700 rounded-full overflow-hidden">
                  <div class="h-full bg-gradient-to-r from-blue-500 to-amber-400 transition-all duration-700" style="width: ${cur.meterPercent}"></div>
                </div>
              </div>

              <p class="text-xs sm:text-sm text-slate-300 leading-relaxed bg-slate-900/60 p-3 rounded-xl border border-slate-700">
                ${cur.fakta}
              </p>
            </div>
          </div>

          <div class="mt-6 pt-4 border-t border-slate-800 flex justify-end">
            <button onclick="completeZone(3)" class="bg-blue-500 hover:bg-blue-400 text-slate-950 px-6 py-2.5 rounded-xl text-xs font-bold font-heading shadow transition">
              Tuntut Lencana Zon 3 ✓
            </button>
          </div>
        </div>
      `;
      lucide.createIcons();
    }

    function z3PickLegend(idx) {
      playSfx('click');
      z3ActiveIndex = idx;
      renderZone3Interactive();
    }

    // ========================================================
    // ZON 4: PENGUKUR REKOD DUNIA PARALIMPIK (SP 12.1.4)
    // ========================================================
    let z4Measured = 0; // nilai slider
    function renderZone4Interactive() {
      const area = document.getElementById('zone-content-area');
      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-blue-400/20 text-blue-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-blue-400/30">
              SP 12.1.4 • ZON 4: PENGUKUR REKOD DUNIA PARALIMPIK
            </span>
            <button onclick="returnToHub()" class="text-xs font-bold text-slate-400 hover:text-rose-400 font-heading">Menu Utama</button>
          </div>

          <div class="bg-slate-800/80 p-5 rounded-3xl border border-blue-400/40 mb-6 text-center">
            <span class="bg-blue-500/20 text-blue-300 text-[11px] font-bold px-3 py-1 rounded-full uppercase tracking-wider font-heading">Slogan: "Kami Luar Biasa"</span>
            <h3 class="text-lg font-bold text-white font-heading mt-2">Uji Ukuran Rekod Dunia Lompat Jauh Abdul Latif bin Romly (Rio 2016)</h3>
            <p class="text-xs text-slate-300 mt-1">Gerakkan penunjuk pita pengukur di bawah ke jarak lompatan rekod dunia yang betul:</p>
          </div>

          <!-- Slider Pita Pengukur Interaktif -->
          <div class="bg-slate-900/90 p-6 rounded-3xl border border-slate-700 flex flex-col items-center">
            <div class="text-3xl font-extrabold text-amber-400 font-heading mb-2" id="z4-display-val">
              5.00 m
            </div>

            <input type="range" id="z4-slider" min="5.00" max="10.00" step="0.10" value="5.00" oninput="z4UpdateSlider(this.value)" class="w-full max-w-md accent-amber-400 cursor-pointer">

            <div class="flex justify-between w-full max-w-md text-xs text-slate-400 mt-2 font-bold font-heading">
              <span>5.00 m</span>
              <span>7.00 m</span>
              <span>8.00 m</span>
              <span>10.00 m</span>
            </div>

            <button onclick="z4VerifyMeasurement()" class="mt-5 bg-gradient-to-r from-blue-500 to-amber-500 text-slate-950 font-bold px-6 py-2.5 rounded-xl font-heading text-xs shadow-md hover:opacity-90 transition">
              Sahkan Ukuran Lompatan
            </button>
          </div>

          <div id="z4-feedback" class="mt-4 hidden p-4 rounded-2xl text-xs sm:text-sm"></div>
        </div>
      `;
      lucide.createIcons();
    }

    function z4UpdateSlider(val) {
      z4Measured = parseFloat(val);
      document.getElementById('z4-display-val').textContent = `${parseFloat(val).toFixed(2)} m`;
    }

    function z4VerifyMeasurement() {
      const fb = document.getElementById('z4-feedback');
      fb.classList.remove('hidden');

      if (Math.abs(z4Measured - 7.60) < 0.15) {
        playSfx('correct');
        confetti({ particleCount: 50, spread: 60 });
        fb.className = "mt-4 p-4 rounded-2xl bg-emerald-950/70 border border-emerald-400 text-emerald-200";
        fb.innerHTML = `
          <strong>Luar Biasa! Tepat Sekali!</strong> Lompatan rekod dunia Abdul Latif Romly di Rio 2016 ialah <strong>7.60 meter</strong>! Beliau juga mempertahankan emas di Tokyo 2020!
          <button onclick="completeZone(4)" class="mt-3 block bg-emerald-400 text-slate-950 font-bold px-4 py-1.5 rounded-xl text-xs font-heading">Tuntut Lencana Zon 4 ✓</button>
        `;
      } else {
        playSfx('click');
        fb.className = "mt-4 p-4 rounded-2xl bg-rose-950/70 border border-rose-400 text-rose-200";
        fb.innerHTML = `Ukuran semasa (${z4Measured.toFixed(2)}m) belum tepat. Petunjuk: Rekod dunia beliau ialah sekitar <strong>7.60 meter</strong>. Sila laraskan slider!`;
      }
    }

    // ========================================================
    // ZON 5: PENGATUR PADANG HARMONI SEKOLAH (SP 12.1.1)
    // ========================================================
    let z5Placed = { rimup: false, dasar1m1s: false, mssm: false };
    function renderZone5Interactive() {
      const area = document.getElementById('zone-content-area');
      const allDone = z5Placed.rimup && z5Placed.dasar1m1s && z5Placed.mssm;

      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-emerald-400/20 text-emerald-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-emerald-400/30">
              SP 12.1.1 • ZON 5: PENGATUR PADANG HARMONI SEKOLAH
            </span>
            <button onclick="returnToHub()" class="text-xs font-bold text-slate-400 hover:text-rose-400 font-heading">Menu Utama</button>
          </div>

          <p class="text-xs text-slate-300 mb-3">Klik setiap dasar perpaduan untuk menempatkannya ke dalam Padang Muhibah dan menyalakan Obor Integrasi:</p>

          <div class="grid grid-cols-1 sm:grid-cols-3 gap-3 mb-6">
            <button onclick="z5PlaceProgram('rimup')" class="p-4 rounded-2xl border-2 text-left transition font-heading ${
              z5Placed.rimup ? 'bg-emerald-900/60 border-emerald-400 text-emerald-200' : 'bg-slate-800 border-slate-700 hover:border-emerald-400 text-slate-200'
            }">
              <span class="text-xl">🏫</span>
              <h4 class="font-bold text-xs mt-1">1. RIMUP (2005)</h4>
              <p class="text-[10px] opacity-80 mt-0.5">Kerjasama sukan antara sekolah berlainan aliran.</p>
              ${z5Placed.rimup ? '<span class="text-[9px] text-emerald-400 font-bold">✓ Ditempatkan</span>' : '<span class="text-[9px] text-amber-400">Tekan untuk letak</span>'}
            </button>

            <button onclick="z5PlaceProgram('dasar1m1s')" class="p-4 rounded-2xl border-2 text-left transition font-heading ${
              z5Placed.dasar1m1s ? 'bg-emerald-900/60 border-emerald-400 text-emerald-200' : 'bg-slate-800 border-slate-700 hover:border-emerald-400 text-slate-200'
            }">
              <span class="text-xl">🏃‍♀️</span>
              <h4 class="font-bold text-xs mt-1">2. Dasar 1M1S (2011)</h4>
              <p class="text-[10px] opacity-80 mt-0.5">Wajib 1 murid sertai sekurang-kurangnya 1 sukan.</p>
              ${z5Placed.dasar1m1s ? '<span class="text-[9px] text-emerald-400 font-bold">✓ Ditempatkan</span>' : '<span class="text-[9px] text-amber-400">Tekan untuk letak</span>'}
            </button>

            <button onclick="z5PlaceProgram('mssm')" class="p-4 rounded-2xl border-2 text-left transition font-heading ${
              z5Placed.mssm ? 'bg-emerald-900/60 border-emerald-400 text-emerald-200' : 'bg-slate-800 border-slate-700 hover:border-emerald-400 text-slate-200'
            }">
              <span class="text-xl">🦁</span>
              <h4 class="font-bold text-xs mt-1">3. MSSM Tahunan</h4>
              <p class="text-[10px] opacity-80 mt-0.5">Medan atlet remaja membina bakat & perpaduan.</p>
              ${z5Placed.mssm ? '<span class="text-[9px] text-emerald-400 font-bold">✓ Ditempatkan</span>' : '<span class="text-[9px] text-amber-400">Tekan untuk letak</span>'}
            </button>
          </div>

          <!-- Pentas Padang Visual Perpaduan -->
          <div class="bg-gradient-to-b from-emerald-950/60 to-slate-900 p-6 rounded-3xl border border-emerald-500/40 text-center relative overflow-hidden">
            <div class="text-5xl mb-2 ${allDone ? 'anim-jump' : ''}">
              ${allDone ? '🔥🤝🇲🇾' : '🏟️✨'}
            </div>
            <h3 class="text-base font-bold text-white font-heading">
              ${allDone ? 'Obor Perpaduan Menyala Megah di Padang Sekolah!' : 'Padang Menunggu Dasar Perpaduan Dilengkapkan...'}
            </h3>
            <p class="text-xs text-slate-300 mt-1 max-w-md mx-auto">
              ${allDone ? 'Ketiga-tiga inisiatif ini membuktikan sukan bertindak sebagai tali pengikat keharmonian masyarakat Malaysia pelbagai kaum!' : 'Klik ketiga-tiga kad program di atas untuk menyempurnakan pembentukan perpaduan.'}
            </p>
          </div>

          <div class="mt-6 pt-4 border-t border-slate-800 flex justify-end">
            <button onclick="${allDone ? 'completeZone(5)' : 'alert(\'Sila klik ketiga-tiga program terlebih dahulu!\')'}" class="bg-emerald-500 hover:bg-emerald-400 text-slate-950 px-6 py-2.5 rounded-xl text-xs font-bold font-heading shadow transition ${!allDone ? 'opacity-50' : ''}">
              Tuntut Lencana Zon 5 ✓
            </button>
          </div>
        </div>
      `;
      lucide.createIcons();
    }

    function z5PlaceProgram(key) {
      playSfx('click');
      z5Placed[key] = true;
      if (z5Placed.rimup && z5Placed.dasar1m1s && z5Placed.mssm) {
        playSfx('correct');
        confetti({ particleCount: 40, spread: 50 });
      }
      renderZone5Interactive();
    }

    // ========================================================
    // ZON 6: BILIK RUNDINGAN EJEN PERPADUAN (SP 12.1.1)
    // ========================================================
    let z6HarmonyMeter = 40;
    function renderZone6Interactive() {
      const area = document.getElementById('zone-content-area');
      area.innerHTML = `
        <div>
          <div class="flex items-center justify-between pb-4 border-b border-slate-800 mb-5">
            <span class="bg-emerald-400/20 text-emerald-300 text-xs font-bold px-3 py-1 rounded-full font-heading border border-emerald-400/30">
              SP 12.1.1 • ZON 6: BILIK RUNDINGAN EJEN PERPADUAN
            </span>
            <button onclick="returnToHub()" class="text-xs font-bold text-slate-400 hover:text-rose-400 font-heading">Menu Utama</button>
          </div>

          <!-- Tolok Meter Keharmonian Pasukan -->
          <div class="mb-5 bg-slate-800/80 p-4 rounded-2xl border border-slate-700 flex items-center justify-between gap-4">
            <span class="text-xs font-bold text-slate-300 flex items-center gap-1.5 font-heading">
              <i data-lucide="heart" class="w-4 h-4 text-rose-500"></i> Meter Keharmonian Pasukan:
            </span>
            <div class="w-48 h-3.5 bg-slate-700 rounded-full overflow-hidden">
              <div id="z6-meter-bar" class="h-full bg-gradient-to-r from-amber-400 to-emerald-400 transition-all duration-500" style="width: ${z6HarmonyMeter}%"></div>
            </div>
            <span id="z6-meter-label" class="text-xs font-bold text-emerald-400 font-heading">${z6HarmonyMeter}%</span>
          </div>

          <div class="bg-slate-800/90 p-5 rounded-3xl border-2 border-emerald-400/40 mb-6">
            <h4 class="text-sm sm:text-base font-bold text-white font-heading">
              Situasi Bilik Rundingan: Pasukan bola sepak sekolah tewas tipis pada minit akhir. Pemain penyerang berasa kecewa lalu mula menyalahkan penjaga gol daripada kaum lain di hadapan semua rakan sepasukan.
            </h4>
            <p class="text-xs text-slate-300 mt-2">Sebagai Ejen Perpaduan Sukan sekolah, apakah keputusan bijaksana yang anda ambil?</p>
          </div>

          <div class="space-y-3">
            <button onclick="z6ResolveConflict(true)" class="w-full text-left p-4 rounded-2xl bg-slate-800 hover:bg-slate-700 border-2 border-slate-700 hover:border-emerald-400 transition-all font-semibold text-xs sm:text-sm">
              A. Tenangkan keadaan, ingatkan bahawa sukan mengajar erti kerjasama dan saling menghormati, lalu minta mereka berjabat tangan dan berikrar berjuang bersama pada masa depan.
            </button>
            <button onclick="z6ResolveConflict(false)" class="w-full text-left p-4 rounded-2xl bg-slate-800 hover:bg-slate-700 border-2 border-slate-700 hover:border-rose-400 transition-all font-semibold text-xs sm:text-sm">
              B. Membiarkan mereka bertengkar dan meminta pemain yang bersalah disisihkan daripada menyertai sukan sekolah.
            </button>
          </div>

          <div id="z6-feedback" class="mt-4 hidden p-4 rounded-2xl text-xs sm:text-sm"></div>
        </div>
      `;
      lucide.createIcons();
    }

    function z6ResolveConflict(isPeace) {
      const fb = document.getElementById('z6-feedback');
      fb.classList.remove('hidden');

      if (isPeace) {
        playSfx('correct');
        z6HarmonyMeter = 100;
        document.getElementById('z6-meter-bar').style.width = '100%';
        document.getElementById('z6-meter-label').textContent = '100% (Harmoni Penuh!)';
        confetti({ particleCount: 50, spread: 70 });
        fb.className = "mt-4 p-4 rounded-2xl bg-emerald-950/70 border border-emerald-400 text-emerald-200";
        fb.innerHTML = `
          <strong>Keputusan Mulia!</strong> Kedua-dua pemain saling berpelukan dan bermaafan. Sorakan perpaduan bergema di bilik persalinan!
          <button onclick="completeZone(6)" class="mt-3 block bg-emerald-400 text-slate-950 font-bold px-4 py-1.5 rounded-xl text-xs font-heading">Tuntut Lencana Zon 6 ✓</button>
        `;
      } else {
        playSfx('click');
        z6HarmonyMeter = 15;
        document.getElementById('z6-meter-bar').style.width = '15%';
        document.getElementById('z6-meter-label').textContent = '15% (Retak!)';
        fb.className = "mt-4 p-4 rounded-2xl bg-rose-950/70 border border-rose-400 text-rose-200";
        fb.innerHTML = `Tindakan menyisihkan rakan memecahbelahkan keharmonian pasukan! Sila pilih pilihan A untuk memulihkan semangat muhibah.`;
      }
    }

    // ========================================================
    // PENYELESAIAN ZON & PEMBUKAAN SIJIL
    // ========================================================
    function completeZone(zId) {
      playSfx('fanfare');
      confetti({ particleCount: 75, spread: 65, origin: { y: 0.6 } });
      completedZones.add(zId);
      currentScore += 50;
      document.getElementById('player-score').textContent = currentScore;

      const tag = document.getElementById(`badge-tag-${zId}`);
      if (tag) {
        tag.textContent = "SELESAI ✓";
        tag.className = "text-[10px] bg-emerald-400/20 text-emerald-300 border border-emerald-400/40 px-2 py-0.5 rounded-full font-bold";
      }

      returnToHub();
    }

    function openCertificateScreen() {
      playSfx('fanfare');
      confetti({ particleCount: 150, spread: 90, origin: { y: 0.5 } });
      document.getElementById('screen-hub').classList.add('hidden');
      document.getElementById('screen-certificate').classList.remove('hidden');

      const today = new Date();
      document.getElementById('cert-date').textContent = today.toLocaleDateString('ms-MY', {
        day: 'numeric', month: 'long', year: 'numeric'
      });
      lucide.createIcons();
    }

    window.addEventListener('DOMContentLoaded', () => {
      initBadges();
      lucide.createIcons();
    });
  </script>
</body>
</html>
