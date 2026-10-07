<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shree Jagannath Apartment - Maintenance & Society Accounts</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Font Awesome 6 Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  
  <!-- Google Fonts: Inter for UI & Cinzel for Divine Temple Aesthetics -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;800;900&family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      darkMode: 'class',
      theme: {
        extend: {
          colors: {
            saffron: {
              400: '#fbbf24',
              500: '#f59e0b',
              600: '#d97706',
              700: '#b45309',
            },
            temple: {
              gold: '#ffd166',
              vermilion: '#e63946',
              dark: '#070a14',
            }
          },
          fontFamily: {
            sans: ['Inter', 'sans-serif'],
            serif: ['Cinzel', 'serif'],
          }
        }
      }
    }
  </script>

  <style>
    /* Custom Scrollbars */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    ::-webkit-scrollbar-track {
      background: rgba(7, 10, 20, 0.95);
    }
    ::-webkit-scrollbar-thumb {
      background: #f59e0b;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #ffd166;
    }

    /* Glassmorphic Elements */
    .glass-panel {
      background: rgba(13, 20, 38, 0.84);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border: 1px solid rgba(245, 158, 11, 0.22);
    }
    .glass-card {
      background: rgba(20, 30, 52, 0.72);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    }
    .glass-card:hover {
      border-color: rgba(245, 158, 11, 0.45);
      box-shadow: 0 10px 25px -5px rgba(245, 158, 11, 0.15);
    }

    /* Temple Flag Fluttering Animation */
    @keyframes flagSway {
      0%, 100% { transform: skewY(0deg) scaleX(1); }
      50% { transform: skewY(-8deg) scaleX(1.12); }
    }
    .temple-flag {
      animation: flagSway 3.2s ease-in-out infinite;
      transform-origin: left center;
    }

    /* Glowing Badge Pulse for Unpaid Special Works */
    @keyframes alertPulse {
      0%, 100% { box-shadow: 0 0 4px rgba(245, 158, 11, 0.3); }
      50% { box-shadow: 0 0 12px rgba(245, 158, 11, 0.85); }
    }
    .glow-warning {
      animation: alertPulse 2s infinite;
    }

    /* Printable Bill Slip */
    @media print {
      body * {
        visibility: hidden !important;
      }
      #printable-receipt, #printable-receipt * {
        visibility: visible !important;
      }
      #printable-receipt {
        position: absolute !important;
        left: 0 !important;
        top: 0 !important;
        width: 100% !important;
        background: #ffffff !important;
        color: #000000 !important;
        padding: 24px !important;
      }
      .no-print {
        display: none !important;
      }
    }
  </style>
</head>
<body class="bg-[#070a14] text-slate-100 font-sans min-h-screen relative overflow-x-hidden selection:bg-amber-500 selection:text-black">

  <!-- DYNAMIC BACKGROUND: LORD JAGANNATH TEMPLE & APARTMENT SKYLINE -->
  <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
    <canvas id="bg-canvas" class="absolute inset-0 w-full h-full"></canvas>

    <!-- Divine Aurora Radial Glows -->
    <div class="absolute -top-32 left-1/2 -translate-x-1/2 w-[850px] h-[650px] bg-amber-500/15 rounded-full blur-[140px]"></div>
    <div class="absolute top-1/3 left-1/5 w-[500px] h-[500px] bg-sky-600/10 rounded-full blur-[140px]"></div>
    <div class="absolute top-1/3 right-1/5 w-[500px] h-[500px] bg-rose-600/10 rounded-full blur-[130px]"></div>

    <!-- Architectural Silhouette Vector -->
    <div class="absolute bottom-0 inset-x-0 w-full h-[380px] md:h-[460px] opacity-45 md:opacity-55">
      <svg class="w-full h-full" viewBox="0 0 1600 500" preserveAspectRatio="none" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="templeGrad" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="0%" stop-color="#ffd166" stop-opacity="0.95" />
            <stop offset="35%" stop-color="#f59e0b" stop-opacity="0.55" />
            <stop offset="100%" stop-color="#070a14" stop-opacity="0.98" />
          </linearGradient>
          <linearGradient id="bldgGrad" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="0%" stop-color="#38bdf8" stop-opacity="0.45" />
            <stop offset="100%" stop-color="#070a14" stop-opacity="0.98" />
          </linearGradient>
          <filter id="divineGlow" x="-20%" y="-20%" width="140%" height="140%">
            <feGaussianBlur stdDeviation="8" result="blur" />
            <feComposite in="SourceGraphic" in2="blur" operator="over" />
          </filter>
        </defs>

        <!-- Left Modern Apartment Towers (Wing A) -->
        <rect x="30" y="210" width="85" height="290" fill="url(#bldgGrad)" rx="3"/>
        <rect x="125" y="160" width="105" height="340" fill="url(#bldgGrad)" rx="3"/>
        <rect x="240" y="110" width="130" height="390" fill="url(#bldgGrad)" rx="3"/>
        <rect x="380" y="200" width="85" height="300" fill="url(#bldgGrad)" rx="3"/>

        <!-- Wing A Lit Windows -->
        <g fill="#fde68a" opacity="0.7">
          <rect x="145" y="185" width="8" height="12" rx="1"/> <rect x="175" y="185" width="8" height="12" rx="1"/> <rect x="200" y="185" width="8" height="12" rx="1"/>
          <rect x="145" y="220" width="8" height="12" rx="1"/> <rect x="200" y="220" width="8" height="12" rx="1"/>
          <rect x="260" y="135" width="10" height="14" rx="1"/> <rect x="295" y="135" width="10" height="14" rx="1"/> <rect x="330" y="135" width="10" height="14" rx="1"/>
          <rect x="260" y="170" width="10" height="14" rx="1"/> <rect x="330" y="170" width="10" height="14" rx="1"/>
        </g>

        <!-- Center Sacred Shree Jagannath Temple (Rekha Deula) -->
        <g filter="url(#divineGlow)">
          <path d="M590 500 L630 350 L690 300 L760 250 L840 250 L910 300 L970 350 L1010 500 Z" fill="url(#templeGrad)" />
          <path d="M720 280 C 740 190, 770 110, 800 60 C 830 110, 860 190, 880 280 Z" fill="url(#templeGrad)" />
          <path d="M800 60 L800 280" stroke="#ffd166" stroke-width="2.5" opacity="0.6"/>
          <ellipse cx="800" cy="58" rx="24" ry="8" fill="#ffd166" />
          <path d="M793 58 L795 38 L805 38 L807 58 Z" fill="#ffd166" />
          <ellipse cx="800" cy="38" rx="10" ry="5" fill="#ffd166" />

          <!-- Sacred Nilachakra (8-Spoke Wheel) -->
          <g transform="translate(800, 26)">
            <circle cx="0" cy="0" r="15" stroke="#ffd166" stroke-width="3" fill="#0f172a" opacity="0.95" />
            <circle cx="0" cy="0" r="4" fill="#fbbf24" />
            <path d="M0 -15 L0 15 M-15 0 L15 0 M-11 -11 L11 11 M-11 11 L11 -11" stroke="#ffd166" stroke-width="2" />
          </g>

          <!-- Patitapabana Flag -->
          <path d="M800 26 L800 5" stroke="#f59e0b" stroke-width="3" stroke-linecap="round"/>
          <path class="temple-flag" d="M800 5 Q 826 -1, 852 10 Q 865 22, 854 28 L800 18 Z" fill="#e63946" />
        </g>

        <!-- Right Modern Apartment Towers (Wing B) -->
        <rect x="1130" y="140" width="130" height="360" fill="url(#bldgGrad)" rx="3"/>
        <rect x="1275" y="190" width="115" height="310" fill="url(#bldgGrad)" rx="3"/>
        <rect x="1405" y="110" width="145" height="390" fill="url(#bldgGrad)" rx="3"/>

        <!-- Wing B Lit Windows -->
        <g fill="#fde68a" opacity="0.7">
          <rect x="1155" y="170" width="10" height="14" rx="1"/> <rect x="1190" y="170" width="10" height="14" rx="1"/> <rect x="1225" y="170" width="10" height="14" rx="1"/>
          <rect x="1430" y="140" width="12" height="16" rx="1"/> <rect x="1470" y="140" width="12" height="16" rx="1"/> <rect x="1510" y="140" width="12" height="16" rx="1"/>
        </g>
      </svg>
    </div>
  </div>

  <!-- MAIN APP WRAPPER -->
  <div class="relative z-10 flex flex-col min-h-screen">
    
    <!-- TOP ANNOUNCEMENT & BILLING CYCLE BANNER -->
    <div class="bg-gradient-to-r from-amber-600/30 via-amber-500/20 to-amber-600/30 border-b border-amber-500/30 px-4 py-2 text-center text-xs sm:text-sm text-amber-200 flex flex-wrap items-center justify-center gap-3">
      <span class="inline-flex items-center gap-1.5 font-bold text-emerald-400">
        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
        Billing Cycle: <span id="banner-month-name" class="underline decoration-amber-400 font-extrabold ml-1">August 2026</span>
      </span>
      <span class="hidden sm:inline text-amber-400/50">•</span>
      <span class="text-amber-300">Last Date for Payment: <strong class="text-white">10th of every month</strong></span>
      <span class="hidden sm:inline text-amber-400/50">•</span>
      <span class="text-slate-300">Water Tariff: <strong class="text-amber-400" id="banner-water-rate">₹0.15/L</strong> | Standard Maintenance: <strong class="text-amber-400">₹1,000/-</strong></span>
      <span class="hidden md:inline text-amber-400/50">•</span>
      <span id="sync-status-indicator" class="text-[11px] px-2 py-0.5 rounded-full bg-emerald-950/60 text-emerald-300 border border-emerald-500/30 flex items-center gap-1">
        <i class="fa-solid fa-cloud-arrow-up text-[10px]"></i> Live Sync Active
      </span>
    </div>

    <!-- MAIN NAVBAR -->
    <header class="glass-panel border-b border-amber-500/20 sticky top-0 z-30 px-4 sm:px-8 py-3.5 transition-all">
      <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-4">
        
        <!-- Logo & Society Identity -->
        <div class="flex items-center gap-3.5 w-full md:w-auto justify-between md:justify-start">
          <div class="flex items-center gap-3">
            <div class="relative flex items-center justify-center w-12 h-12 rounded-2xl bg-gradient-to-tr from-amber-600 to-amber-400 shadow-lg shadow-amber-500/25 border border-amber-300/40 shrink-0">
              <svg class="w-8 h-8 text-slate-950" viewBox="0 0 24 24" fill="currentColor">
                <circle cx="12" cy="12" r="10" fill="#070a14" stroke="#ffd166" stroke-width="1.5" />
                <circle cx="12" cy="12" r="7" fill="#ffffff" />
                <circle cx="12" cy="12" r="4.2" fill="#dc2626" />
                <circle cx="12" cy="12" r="2.2" fill="#070a14" />
                <path d="M10 2 C 10 6.5, 12 7.5, 12 7.5 C 12 7.5, 14 6.5, 14 2 Z" fill="#ffd166" />
              </svg>
            </div>
            <div>
              <div class="flex items-center gap-2">
                <h1 class="text-lg sm:text-xl font-bold tracking-tight text-white font-serif">
                  श्री जगन्नाथ अपार्टमेंट
                </h1>
                <span id="role-badge" class="text-[10px] bg-slate-800 text-slate-300 font-sans px-2.5 py-0.5 rounded-full border border-slate-600 font-semibold flex items-center gap-1">
                  <i class="fa-solid fa-eye text-[9px]"></i> Viewer Mode
                </span>
              </div>
              <p class="text-xs text-amber-200/80">
                Maintenance, Water & Society Treasury Ledger
              </p>
            </div>
          </div>

          <!-- Mobile Month Select -->
          <div class="md:hidden">
            <select id="mobile-month-select" onchange="switchMonth(this.value)" class="bg-slate-900 border border-amber-500/40 rounded-xl px-2.5 py-1.5 text-xs text-amber-300 font-bold focus:outline-none">
            </select>
          </div>
        </div>

        <!-- Controls: Month Switcher, Pay QR, Resident Proof, Admin Mode -->
        <div class="flex flex-wrap items-center gap-2.5 w-full md:w-auto justify-end">
          
          <!-- Month Dropdown Selector (Desktop) -->
          <div class="hidden md:flex items-center gap-2 bg-slate-900/90 border border-amber-500/40 rounded-xl px-3 py-1.5 shadow-inner">
            <span class="text-xs text-slate-400 font-medium"><i class="fa-regular fa-calendar text-amber-400 mr-1"></i>Month:</span>
            <select id="desktop-month-select" onchange="switchMonth(this.value)" class="bg-transparent text-xs text-amber-300 font-bold focus:outline-none cursor-pointer">
            </select>
          </div>

          <!-- Dynamic Water Rate Button (Admin) -->
          <button id="admin-rate-btn" onclick="openWaterRateModal()" class="hidden px-3.5 py-2 text-xs rounded-xl font-semibold bg-amber-500/15 hover:bg-amber-500/25 text-amber-300 border border-amber-500/40 flex items-center gap-1.5 transition">
            <i class="fa-solid fa-droplet text-amber-400"></i>
            <span>Set Rate (<span id="btn-curr-rate">₹0.15</span>)</span>
          </button>

          <!-- QR Code Pay Button -->
          <button onclick="openQrModal()" class="px-3.5 py-2 text-xs rounded-xl font-semibold bg-emerald-500/15 hover:bg-emerald-500/25 text-emerald-300 border border-emerald-500/40 flex items-center gap-1.5 transition">
            <i class="fa-solid fa-qrcode text-emerald-400"></i>
            <span>Pay QR / Barcode</span>
          </button>

          <!-- Resident Upload Proof Button -->
          <button onclick="openResidentProofModal()" class="px-3.5 py-2 text-xs rounded-xl font-semibold bg-sky-500/15 hover:bg-sky-500/25 text-sky-300 border border-sky-500/40 flex items-center gap-1.5 transition">
            <i class="fa-solid fa-receipt text-sky-400"></i>
            <span>Upload Receipt</span>
          </button>

          <!-- Admin Login / Logout Trigger -->
          <button id="admin-auth-btn" onclick="handleAuthAction()" class="px-4 py-2 text-xs rounded-xl font-bold bg-gradient-to-r from-amber-500 to-amber-600 hover:from-amber-400 hover:to-amber-500 text-slate-950 shadow-md shadow-amber-500/25 flex items-center gap-1.5 transition">
            <i id="admin-btn-icon" class="fa-solid fa-lock text-slate-950"></i>
            <span id="admin-btn-text">Admin Login</span>
          </button>

          <!-- Admin Change Password Button -->
          <button id="admin-change-pwd-btn" onclick="openChangePasswordModal()" class="hidden px-3 py-2 text-xs rounded-xl font-semibold bg-slate-800 hover:bg-slate-700 text-slate-200 border border-slate-600 transition items-center gap-1.5" title="Change Admin Password">
            <i class="fa-solid fa-key text-amber-400"></i>
            <span class="hidden sm:inline">Passkey</span>
          </button>

        </div>
      </div>
    </header>

    <!-- MASTER FINANCIAL & TREASURY OVERVIEW -->
    <main class="max-w-7xl mx-auto px-4 sm:px-8 py-5 flex-1 w-full space-y-6">
      
      <!-- Master Calculations Dashboard -->
      <section class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-3.5">
        
        <!-- Total Demand Billed -->
        <div class="glass-card p-4 rounded-2xl border-l-4 border-l-amber-500">
          <div class="text-[11px] font-semibold tracking-wider text-amber-400 uppercase flex items-center justify-between">
            <span>Total Demand Billed</span>
            <i class="fa-solid fa-file-invoice-dollar text-amber-500/60"></i>
          </div>
          <div class="mt-1 text-xl sm:text-2xl font-black text-white" id="stat-total-billed">₹231,996.50</div>
          <div class="mt-1 text-[11px] text-slate-400">Wing A + Wing B Consolidated</div>
        </div>

        <!-- Total Collected -->
        <div class="glass-card p-4 rounded-2xl border-l-4 border-l-emerald-500">
          <div class="text-[11px] font-semibold tracking-wider text-emerald-400 uppercase flex items-center justify-between">
            <span>Received / Collected</span>
            <i class="fa-solid fa-circle-check text-emerald-500/60"></i>
          </div>
          <div class="mt-1 text-xl sm:text-2xl font-black text-emerald-400" id="stat-total-received">₹0.00</div>
          <div class="mt-1 text-[11px] text-slate-400 flex items-center justify-between">
            <span id="stat-collection-rate">0% Recovered</span>
            <i class="fa-solid fa-chart-pie text-emerald-400/50"></i>
          </div>
        </div>

        <!-- Pending Outstanding -->
        <div class="glass-card p-4 rounded-2xl border-l-4 border-l-rose-500">
          <div class="text-[11px] font-semibold tracking-wider text-rose-400 uppercase flex items-center justify-between">
            <span>Pending Balance</span>
            <i class="fa-solid fa-clock-rotate-left text-rose-500/60"></i>
          </div>
          <div class="mt-1 text-xl sm:text-2xl font-black text-rose-400" id="stat-total-pending">₹231,996.50</div>
          <div class="mt-1 text-[11px] text-slate-400">Arrears to be collected</div>
        </div>

        <!-- Total Society Expenses / Kharcha -->
        <div class="glass-card p-4 rounded-2xl border-l-4 border-l-cyan-500">
          <div class="text-[11px] font-semibold tracking-wider text-cyan-400 uppercase flex items-center justify-between">
            <span>Society Kharcha (Exp.)</span>
            <i class="fa-solid fa-screwdriver-wrench text-cyan-500/60"></i>
          </div>
          <div class="mt-1 text-xl sm:text-2xl font-black text-cyan-300" id="stat-total-expense">₹0.00</div>
          <div class="mt-1 text-[11px] text-slate-400">Tanker, Motor, Plumber, etc.</div>
        </div>

        <!-- Net Treasury Cash Available -->
        <div class="col-span-2 sm:col-span-1 glass-card p-4 rounded-2xl border-l-4 border-l-purple-500 bg-gradient-to-br from-purple-950/30 to-slate-900/60">
          <div class="text-[11px] font-semibold tracking-wider text-purple-300 uppercase flex items-center justify-between">
            <span>Net Society Cash</span>
            <i class="fa-solid fa-vault text-purple-400/70"></i>
          </div>
          <div class="mt-1 text-xl sm:text-2xl font-black text-purple-200" id="stat-net-fund">₹0.00</div>
          <div class="mt-1 text-[11px] text-slate-400">Collected - Total Kharcha</div>
        </div>

      </section>

      <!-- NAVIGATION TABS & CONTROLS -->
      <section class="glass-panel p-3.5 rounded-2xl flex flex-col md:flex-row items-center justify-between gap-4">
        
        <!-- View Mode Tabs -->
        <div class="flex items-center gap-1.5 p-1 bg-slate-900/90 rounded-xl border border-slate-700/80 w-full md:w-auto overflow-x-auto">
          <button onclick="setViewTab('BOTH')" id="tab-both" class="px-4 py-2 rounded-lg text-xs font-bold transition bg-amber-500 text-slate-950 shadow">
            Both Wings
          </button>
          <button onclick="setViewTab('WING-A')" id="tab-wing-a" class="px-4 py-2 rounded-lg text-xs font-bold transition text-slate-300 hover:text-white hover:bg-slate-800 flex items-center gap-1">
            <span>Wing A Box</span>
            <span class="text-[10px] bg-amber-500/20 text-amber-300 px-1.5 py-0.2 rounded-full">27</span>
          </button>
          <button onclick="setViewTab('WING-B')" id="tab-wing-b" class="px-4 py-2 rounded-lg text-xs font-bold transition text-slate-300 hover:text-white hover:bg-slate-800 flex items-center gap-1">
            <span>Wing B Box</span>
            <span class="text-[10px] bg-sky-500/20 text-sky-300 px-1.5 py-0.2 rounded-full">29</span>
          </button>
          <button onclick="setViewTab('EXPENSES')" id="tab-expenses" class="px-4 py-2 rounded-lg text-xs font-bold transition text-slate-300 hover:text-white hover:bg-slate-800 flex items-center gap-1.5">
            <span>Society Kharcha</span>
            <span id="expense-count-badge" class="bg-cyan-500/20 text-cyan-300 text-[10px] px-1.5 py-0.2 rounded-full border border-cyan-500/30">0</span>
          </button>
          <button onclick="setViewTab('PROOFS')" id="tab-proofs" class="px-4 py-2 rounded-lg text-xs font-bold transition text-slate-300 hover:text-white hover:bg-slate-800 flex items-center gap-1.5">
            <span>Payment Proofs</span>
            <span id="proofs-badge" class="bg-amber-500/30 text-amber-300 text-[10px] px-1.5 py-0.2 rounded-full border border-amber-500/40">0</span>
          </button>
        </div>

        <!-- Search Bar and Rollover Action -->
        <div class="flex items-center gap-2.5 w-full md:w-auto justify-end">
          <div class="relative flex-1 md:w-64">
            <input 
              type="text" 
              id="global-search" 
              oninput="handleSearch(this.value)" 
              placeholder="Search Flat (e.g. G2, B4) or Name..." 
              class="w-full bg-slate-900 border border-slate-700/80 rounded-xl pl-9 pr-3 py-2 text-xs text-slate-200 placeholder-slate-400 focus:outline-none focus:border-amber-400"
            >
            <i class="fa-solid fa-magnifying-glass text-slate-400 absolute left-3 top-2.5 text-xs"></i>
          </div>

          <!-- Admin Quick Action: Rollover to Next Month -->
          <button id="admin-rollover-btn" onclick="openRolloverModal()" class="hidden px-3.5 py-2 text-xs rounded-xl font-bold bg-indigo-600 hover:bg-indigo-500 text-white shadow transition flex items-center gap-1.5 shrink-0">
            <i class="fa-solid fa-forward-step"></i>
            <span>Next Month Roll-Over</span>
          </button>
        </div>

      </section>

      <!-- WING A DEDICATED SECTION BOX -->
      <section id="section-wing-a" class="space-y-4">
        
        <div class="glass-panel p-5 rounded-2xl border border-amber-500/35 bg-gradient-to-r from-amber-950/25 via-slate-900/70 to-slate-900/90 shadow-lg">
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
            
            <div class="flex items-center gap-3">
              <div class="w-11 h-11 rounded-2xl bg-amber-500/20 border border-amber-500/40 flex items-center justify-center font-serif text-xl font-black text-amber-400 shadow-inner">
                A
              </div>
              <div>
                <h2 class="text-base sm:text-lg font-bold text-white flex items-center gap-2">
                  WING A — रेजिडेंट्स वाटर एवं मेंटेनेंस खाता
                </h2>
                <p class="text-xs text-slate-400">
                  Total 27 Flats (G1 - E5) • Standard Maintenance ₹1,000/- (Bindu B5: ₹400/-)
                </p>
              </div>
            </div>

            <!-- Wing A Mini Metrics Bar -->
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-2 text-xs">
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">WATER CONSUMED</span>
                <span id="wing-a-water-used" class="font-bold text-sky-400">210,740 L</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">NET WATER DUES</span>
                <span id="wing-a-net-water" class="font-bold text-amber-300">₹16,870.50</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">TOTAL DEMAND</span>
                <span id="wing-a-demand" class="font-bold text-white">₹47,836.50</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">PENDING BALANCE</span>
                <span id="wing-a-pending" class="font-bold text-rose-400">₹47,836.50</span>
              </div>
            </div>

          </div>
        </div>

        <!-- Wing A Data Table -->
        <div class="glass-panel rounded-2xl overflow-hidden border border-amber-500/20 shadow-xl">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-xs">
              <thead>
                <tr class="bg-slate-900/95 border-b border-slate-700/80 text-slate-300 uppercase tracking-wider text-[11px] font-semibold">
                  <th class="py-3 px-3 text-center">Flat</th>
                  <th class="py-3 px-3">Resident Name</th>
                  <th class="py-3 px-2 text-center">Meter No</th>
                  <th class="py-3 px-2 text-right">Prev Meter</th>
                  <th class="py-3 px-2 text-right">Curr Meter</th>
                  <th class="py-3 px-3 text-right">Water Used (L)</th>
                  <th class="py-3 px-2 text-right">Net Water (₹)</th>
                  <th class="py-3 px-2 text-right">Maint. (₹)</th>
                  <th class="py-3 px-2 text-right">Old Bal (₹)</th>
                  <th class="py-3 px-3 text-right bg-amber-500/10 text-amber-300 font-bold">Total Payable</th>
                  <th class="py-3 px-3 text-right bg-emerald-500/10 text-emerald-300 font-bold">Received (₹)</th>
                  <th class="py-3 px-3 text-right bg-rose-500/10 text-rose-300 font-bold">Balance (₹)</th>
                  <th class="py-3 px-2 text-center">Status</th>
                  <th class="py-3 px-3 text-center">Action</th>
                </tr>
              </thead>
              <tbody id="table-wing-a-body" class="divide-y divide-slate-800/70 font-normal">
              </tbody>
            </table>
          </div>
        </div>

      </section>

      <!-- WING B DEDICATED SECTION BOX -->
      <section id="section-wing-b" class="space-y-4">
        
        <div class="glass-panel p-5 rounded-2xl border border-sky-500/35 bg-gradient-to-r from-sky-950/25 via-slate-900/70 to-slate-900/90 shadow-lg">
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
            
            <div class="flex items-center gap-3">
              <div class="w-11 h-11 rounded-2xl bg-sky-500/20 border border-sky-500/40 flex items-center justify-center font-serif text-xl font-black text-sky-400 shadow-inner">
                B
              </div>
              <div>
                <h2 class="text-base sm:text-lg font-bold text-white flex items-center gap-2">
                  WING B — रेजिडेंट्स वाटर, मेंटेनेंस व विशेष कार्य खाता
                </h2>
                <p class="text-xs text-slate-400">
                  Total 29 Flats • Includes Electricity Work (₹1,040) & Shaft Work (₹1,000 / ₹2,000)
                </p>
              </div>
            </div>

            <!-- Wing B Mini Metrics Bar -->
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-2 text-xs">
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">WATER CONSUMED</span>
                <span id="wing-b-water-used" class="font-bold text-sky-400">186,700 L</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">NET WATER DUES</span>
                <span id="wing-b-net-water" class="font-bold text-amber-300">₹12,374.50</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">TOTAL DEMAND</span>
                <span id="wing-b-demand" class="font-bold text-white">₹184,160.00</span>
              </div>
              <div class="bg-slate-900/80 px-3 py-2 rounded-xl border border-slate-800">
                <span class="text-slate-400 block text-[10px]">PENDING BALANCE</span>
                <span id="wing-b-pending" class="font-bold text-rose-400">₹184,160.00</span>
              </div>
            </div>

          </div>
        </div>

        <!-- Wing B Data Table -->
        <div class="glass-panel rounded-2xl overflow-hidden border border-sky-500/20 shadow-xl">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-xs">
              <thead>
                <tr class="bg-slate-900/95 border-b border-slate-700/80 text-slate-300 uppercase tracking-wider text-[11px] font-semibold">
                  <th class="py-3 px-3 text-center">Flat</th>
                  <th class="py-3 px-3">Resident Name</th>
                  <th class="py-3 px-2 text-center">Meter No</th>
                  <th class="py-3 px-2 text-right">Prev Meter</th>
                  <th class="py-3 px-2 text-right">Curr Meter</th>
                  <th class="py-3 px-3 text-right">Water Used (L)</th>
                  <th class="py-3 px-2 text-right">Net Water (₹)</th>
                  <th class="py-3 px-2 text-right">Maint. (₹)</th>
                  <th class="py-3 px-2 text-center text-amber-400">Special Work Charges</th>
                  <th class="py-3 px-2 text-right">Old Bal (₹)</th>
                  <th class="py-3 px-3 text-right bg-amber-500/10 text-amber-300 font-bold">Total Payable</th>
                  <th class="py-3 px-3 text-right bg-emerald-500/10 text-emerald-300 font-bold">Received (₹)</th>
                  <th class="py-3 px-3 text-right bg-rose-500/10 text-rose-300 font-bold">Balance (₹)</th>
                  <th class="py-3 px-2 text-center">Status</th>
                  <th class="py-3 px-3 text-center">Action</th>
                </tr>
              </thead>
              <tbody id="table-wing-b-body" class="divide-y divide-slate-800/70 font-normal">
              </tbody>
            </table>
          </div>
        </div>

      </section>

      <!-- SECTION: SOCIETY EXPENSES (KHARCHA TRACKER) -->
      <section id="section-expenses" class="hidden space-y-4">
        
        <div class="glass-panel p-5 rounded-2xl border border-cyan-500/30 bg-gradient-to-r from-cyan-950/20 via-slate-900 to-slate-900 flex flex-col md:flex-row items-center justify-between gap-4">
          <div>
            <h2 class="text-base sm:text-lg font-bold text-white flex items-center gap-2">
              <i class="fa-solid fa-receipt text-cyan-400"></i>
              सोसाइटी खर्च एवं मेंटेनेंस खाता (Apartment Kharcha Ledger)
            </h2>
            <p class="text-xs text-slate-400">
              Track building expenditures like Water Tanker, Guard, Electrician, Plumber, Lift AMC, Motor repair, etc.
            </p>
          </div>

          <button id="add-expense-btn" onclick="openAddExpenseModal()" class="px-4 py-2 text-xs rounded-xl font-bold bg-cyan-600 hover:bg-cyan-500 text-white shadow transition flex items-center gap-1.5">
            <i class="fa-solid fa-plus"></i>
            <span>Add Society Expense</span>
          </button>
        </div>

        <!-- Expenses Table -->
        <div class="glass-panel rounded-2xl overflow-hidden border border-cyan-500/20 shadow-xl">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-xs">
              <thead>
                <tr class="bg-slate-900/90 border-b border-slate-700/80 text-slate-300 uppercase tracking-wider text-[11px] font-semibold">
                  <th class="py-3 px-4">Date</th>
                  <th class="py-3 px-4">Expense Description</th>
                  <th class="py-3 px-3">Category</th>
                  <th class="py-3 px-3">Paid To / Vendor</th>
                  <th class="py-3 px-3 text-right">Amount (₹)</th>
                  <th class="py-3 px-3 text-center">Receipt Voucher</th>
                  <th class="py-3 px-3 text-center">Action</th>
                </tr>
              </thead>
              <tbody id="expenses-table-body" class="divide-y divide-slate-800/70 font-normal">
              </tbody>
            </table>
          </div>
        </div>

      </section>

      <!-- SECTION: RESIDENT PAYMENT PROOFS (SUBMITTED SLIPS) -->
      <section id="section-proofs" class="hidden space-y-4">
        
        <div class="glass-panel p-5 rounded-2xl border border-amber-500/30 bg-gradient-to-r from-amber-950/20 via-slate-900 to-slate-900 flex flex-col md:flex-row items-center justify-between gap-4">
          <div>
            <h2 class="text-base sm:text-lg font-bold text-white flex items-center gap-2">
              <i class="fa-solid fa-clipboard-check text-amber-400"></i>
              रेजिडेंट्स ऑनलाइन पेमेंट सत्यापन (Payment Verification Queue)
            </h2>
            <p class="text-xs text-slate-400">
              Residents scan QR code and upload screenshot/UTR. Admin can inspect receipt and click Approve to credit payment.
            </p>
          </div>
        </div>

        <!-- Proofs Table -->
        <div class="glass-panel rounded-2xl overflow-hidden border border-amber-500/20 shadow-xl">
          <div class="overflow-x-auto">
            <table class="w-full text-left border-collapse text-xs">
              <thead>
                <tr class="bg-slate-900/90 border-b border-slate-700/80 text-slate-300 uppercase tracking-wider text-[11px] font-semibold">
                  <th class="py-3 px-3">Submitted At</th>
                  <th class="py-3 px-3">Flat & Wing</th>
                  <th class="py-3 px-3">Resident Name</th>
                  <th class="py-3 px-3">Amount (₹)</th>
                  <th class="py-3 px-3">UTR / Txn ID</th>
                  <th class="py-3 px-3 text-center">Receipt Screenshot</th>
                  <th class="py-3 px-3 text-center">Status</th>
                  <th class="py-3 px-3 text-center">Admin Action</th>
                </tr>
              </thead>
              <tbody id="proofs-table-body" class="divide-y divide-slate-800/70 font-normal">
              </tbody>
            </table>
          </div>
        </div>

      </section>

    </main>

    <!-- FOOTER -->
    <footer class="border-t border-slate-800/80 bg-slate-950/80 py-5 px-4 text-center text-xs text-slate-500 relative z-20">
      <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-3">
        <div class="flex items-center gap-2">
          <span class="text-amber-400 font-serif font-bold">॥ जय जगन्नाथ ॥</span>
          <span>Shree Jagannath Apartment RWA Management System</span>
        </div>
        <div>
          Admin Contact: <strong class="text-slate-300">7053600701</strong> • Last Date for Payment: 10th of every month
        </div>
      </div>
    </footer>

  </div>

  <!-- MODAL 1: ADMIN LOGIN MODAL -->
  <div id="modal-admin-login" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-admin-login')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <div class="text-center">
        <div class="w-12 h-12 rounded-2xl bg-amber-500/20 border border-amber-500/40 mx-auto flex items-center justify-center text-amber-400 mb-3">
          <i class="fa-solid fa-shield-halved text-xl"></i>
        </div>
        <h3 class="text-lg font-bold font-serif text-white">Admin Security Access</h3>
        <p class="text-xs text-slate-400 mt-1">Authorized RWA Committee Access Only</p>
      </div>

      <form onsubmit="submitAdminLogin(event)" class="mt-5 space-y-4 text-xs">
        <div>
          <label class="block text-slate-300 font-medium mb-1">Registered Mobile Number</label>
          <input type="text" id="login-mobile" placeholder="Enter Mobile (7053600701)" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-amber-400">
        </div>
        <div>
          <label class="block text-slate-300 font-medium mb-1">Password</label>
          <input type="password" id="login-password" placeholder="Enter Password" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-amber-400">
        </div>
        <div id="login-error" class="text-rose-400 text-xs hidden">Invalid Mobile Number or Password.</div>
        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-amber-500 hover:bg-amber-400 text-slate-950 transition">
          Unlock Admin Dashboard
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 1B: ADMIN CHANGE PASSWORD MODAL -->
  <div id="modal-change-password" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-change-password')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <div class="text-center">
        <div class="w-12 h-12 rounded-2xl bg-amber-500/20 border border-amber-500/40 mx-auto flex items-center justify-center text-amber-400 mb-3">
          <i class="fa-solid fa-key text-xl"></i>
        </div>
        <h3 class="text-lg font-bold font-serif text-white">Change Admin Password</h3>
        <p class="text-xs text-slate-400 mt-1">Update your society management passkey</p>
      </div>

      <form onsubmit="submitChangePassword(event)" class="mt-5 space-y-4 text-xs">
        <div>
          <label class="block text-slate-300 font-medium mb-1">Current Password</label>
          <input type="password" id="cur-pass-input" placeholder="Current Password" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-amber-400">
        </div>
        <div>
          <label class="block text-slate-300 font-medium mb-1">New Password</label>
          <input type="password" id="new-pass-input" placeholder="New Password" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white focus:outline-none focus:border-amber-400">
        </div>
        <div id="change-pass-error" class="text-rose-400 text-xs hidden">Current password did not match.</div>
        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-amber-500 hover:bg-amber-400 text-slate-950 transition">
          Update & Save Password
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 1C: DYNAMIC WATER RATE MODAL -->
  <div id="modal-water-rate" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-water-rate')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <div class="text-center">
        <div class="w-12 h-12 rounded-2xl bg-sky-500/20 border border-sky-500/40 mx-auto flex items-center justify-center text-sky-400 mb-3">
          <i class="fa-solid fa-droplet text-xl"></i>
        </div>
        <h3 class="text-lg font-bold font-serif text-white">Dynamic Water Rate</h3>
        <p class="text-xs text-slate-400 mt-1">Set rate per litre for active billing cycle</p>
      </div>

      <form onsubmit="submitWaterRateChange(event)" class="mt-5 space-y-4 text-xs">
        <div>
          <label class="block text-slate-300 font-medium mb-1">Rate per Litre (₹)</label>
          <input type="number" step="0.01" id="input-new-water-rate" placeholder="e.g. 0.15" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3.5 py-2.5 text-white font-mono font-bold text-sm focus:outline-none focus:border-amber-400">
        </div>
        <p class="text-[11px] text-slate-400">
          * Updating this rate recalculates the gross water cost for all Wing A & Wing B flats automatically in real-time.
        </p>
        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-amber-500 hover:bg-amber-400 text-slate-950 transition">
          Apply & Recalculate Ledger
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 2: QR CODE PAYMENT & ADMIN UPLOAD -->
  <div id="modal-qr" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-md w-full p-6 shadow-2xl relative text-slate-100 text-center">
      <button onclick="closeModal('modal-qr')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <span class="px-2.5 py-1 bg-emerald-500/20 text-emerald-300 rounded-full text-[10px] font-bold uppercase tracking-wider border border-emerald-500/30">
        Official Society UPI QR
      </span>
      <h3 class="text-lg font-bold font-serif text-white mt-2">Scan & Pay Maintenance</h3>
      <p class="text-xs text-slate-400">Shree Jagannath Apartment RWA Society Account</p>

      <!-- QR Display Container -->
      <div class="mt-4 p-4 bg-white rounded-2xl mx-auto max-w-[240px] shadow-lg flex items-center justify-center min-h-[240px]" id="qr-image-container">
      </div>

      <div class="mt-3 bg-slate-800/80 p-3 rounded-xl border border-slate-700 text-xs text-left">
        <div class="flex justify-between py-0.5">
          <span class="text-slate-400">UPI ID:</span>
          <span class="font-bold text-amber-300 font-mono" id="display-upi-id">7053600701@upi</span>
        </div>
        <div class="flex justify-between py-0.5">
          <span class="text-slate-400">Account:</span>
          <span class="font-bold text-white">Shree Jagannath Apartment RWA</span>
        </div>
      </div>

      <!-- Admin QR Customization Section -->
      <div id="admin-qr-controls" class="mt-4 pt-3 border-t border-slate-800 text-left hidden">
        <label class="block text-amber-400 font-semibold text-xs mb-1">Admin: Upload Custom QR Code / Barcode Image</label>
        <input type="file" id="admin-qr-file-input" accept="image/*" onchange="handleAdminQrUpload(event)" class="w-full text-xs text-slate-300 file:mr-2 file:py-1.5 file:px-3 file:rounded-lg file:border-0 file:text-xs file:font-semibold file:bg-amber-500 file:text-slate-950 hover:file:bg-amber-400 cursor-pointer">
      </div>

      <div class="mt-4 flex gap-2">
        <button onclick="closeModal('modal-qr'); openResidentProofModal();" class="flex-1 py-2.5 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold rounded-xl text-xs transition">
          I Have Paid (Upload Receipt)
        </button>
      </div>
    </div>
  </div>

  <!-- MODAL 3: RESIDENT PAYMENT RECEIPT UPLOAD -->
  <div id="modal-resident-proof" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-md w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-resident-proof')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <h3 class="text-lg font-bold font-serif text-white">Submit Payment Receipt</h3>
      <p class="text-xs text-slate-400 mt-0.5">Upload your payment screenshot or enter transaction UTR.</p>

      <form onsubmit="submitResidentProof(event)" class="mt-4 space-y-3.5 text-xs">
        <div>
          <label class="block text-slate-300 mb-1 font-medium">Select Flat Number</label>
          <select id="proof-flat-select" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white focus:outline-none focus:border-amber-400">
          </select>
        </div>

        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Amount Paid (₹)</label>
            <input type="number" step="0.5" id="proof-amount" required placeholder="e.g. 1954" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white focus:outline-none focus:border-amber-400">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Payment Date</label>
            <input type="date" id="proof-date" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white focus:outline-none focus:border-amber-400">
          </div>
        </div>

        <div>
          <label class="block text-slate-300 mb-1 font-medium">UPI Ref / UTR / Txn Number</label>
          <input type="text" id="proof-utr" required placeholder="12-digit UTR or Txn ID" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white focus:outline-none focus:border-amber-400">
        </div>

        <div>
          <label class="block text-slate-300 mb-1 font-medium">Attach Screenshot / Receipt Image</label>
          <input type="file" id="proof-image-file" accept="image/*" class="w-full text-xs text-slate-300 file:mr-2 file:py-1.5 file:px-3 file:rounded-lg file:border-0 file:text-xs file:font-semibold file:bg-sky-500 file:text-slate-950 hover:file:bg-sky-400 cursor-pointer">
        </div>

        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-amber-500 hover:bg-amber-400 text-slate-950 transition">
          Submit to Society Office
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 4: ADMIN FULL FLAT EDIT MODAL -->
  <div id="modal-edit-flat" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-3 sm:p-4 overflow-y-auto">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-lg w-full p-6 shadow-2xl relative text-slate-100 max-h-[95vh] overflow-y-auto">
      <button onclick="closeModal('modal-edit-flat')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <h3 class="text-base font-bold text-amber-400 flex items-center gap-2">
        <i class="fa-solid fa-pen-to-square"></i>
        <span>Admin: Edit Flat Record & Readings</span>
      </h3>
      <p id="edit-flat-subtitle" class="text-xs text-slate-300 mt-1">Flat Details</p>

      <form onsubmit="submitEditFlat(event)" class="mt-4 space-y-3.5 text-xs">
        <input type="hidden" id="edit-flat-id">

        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Resident Name</label>
            <input type="text" id="edit-flat-name" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Meter Number</label>
            <input type="text" id="edit-flat-meter" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
        </div>

        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Prev Meter Reading</label>
            <input type="number" id="edit-flat-prev" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Current Meter Reading</label>
            <input type="number" id="edit-flat-curr" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
        </div>

        <div class="grid grid-cols-3 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Water Advance (₹)</label>
            <input type="number" id="edit-flat-adv" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Rate per Litre</label>
            <input type="number" step="0.01" id="edit-flat-rate" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Maintenance (₹)</label>
            <input type="number" id="edit-flat-maint" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
        </div>

        <div class="grid grid-cols-3 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Electricity Work (₹)</label>
            <input type="number" id="edit-flat-elec" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Shaft Work (₹)</label>
            <input type="number" id="edit-flat-shaft" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Old Arrears / Bal (₹)</label>
            <input type="number" id="edit-flat-oldbal" oninput="recalcEditRow()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
        </div>

        <div class="grid grid-cols-2 gap-2 bg-slate-800/60 p-3 rounded-xl border border-slate-700">
          <div>
            <label class="block text-amber-300 mb-1 font-bold">Auto-Calculated Demand (₹)</label>
            <input type="number" step="0.5" id="edit-flat-needpay" readonly class="w-full bg-slate-900 border border-amber-500/40 rounded-xl px-3 py-2 text-amber-300 font-black">
          </div>
          <div>
            <label class="block text-emerald-400 mb-1 font-bold">Payment Received (₹)</label>
            <input type="number" step="0.5" id="edit-flat-paid" class="w-full bg-slate-900 border border-emerald-500/40 rounded-xl px-3 py-2 text-emerald-300 font-black">
          </div>
        </div>

        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-amber-500 hover:bg-amber-400 text-slate-950 transition">
          Save Updates & Sync Real-Time
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 5: ADD SOCIETY EXPENSE (KHARCHA) -->
  <div id="modal-add-expense" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-cyan-500/40 rounded-3xl max-w-md w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-add-expense')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <h3 class="text-base font-bold text-cyan-300 flex items-center gap-2">
        <i class="fa-solid fa-plus-circle"></i>
        <span>Add Society Expenditure (खर्च)</span>
      </h3>
      <p class="text-xs text-slate-400 mt-0.5">Recorded directly in the building maintenance ledger.</p>

      <form onsubmit="submitSocietyExpense(event)" class="mt-4 space-y-3 text-xs">
        <div>
          <label class="block text-slate-300 mb-1 font-medium">Expense Title / Item</label>
          <input type="text" id="expense-title" placeholder="e.g. Water Tanker Supply (5000L), Plumber, Lift AMC" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white focus:outline-none focus:border-cyan-400">
        </div>

        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Category</label>
            <select id="expense-category" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
              <option value="Water Tanker">Water Tanker Supply</option>
              <option value="Water Motor">Borewell / Motor Servicing</option>
              <option value="Electricity">Electricity / Wiring</option>
              <option value="Lift">Lift Maintenance / AMC</option>
              <option value="Shaft/Plumbing">Plumber / Shaft Repair</option>
              <option value="Staff/Guard">Guard / Sweeper Salary</option>
              <option value="General">General Society Repair</option>
            </select>
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Amount (₹)</label>
            <input type="number" step="0.5" id="expense-amount" placeholder="e.g. 4500" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white font-bold focus:outline-none focus:border-cyan-400">
          </div>
        </div>

        <div class="grid grid-cols-2 gap-2">
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Expense Date</label>
            <input type="date" id="expense-date" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
          <div>
            <label class="block text-slate-300 mb-1 font-medium">Paid To (Vendor / Person)</label>
            <input type="text" id="expense-vendor" placeholder="e.g. Krishna Water Supply" required class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-white">
          </div>
        </div>

        <div>
          <label class="block text-slate-300 mb-1 font-medium">Upload Receipt / Voucher Photo</label>
          <input type="file" id="expense-voucher-file" accept="image/*" class="w-full text-xs text-slate-300 file:mr-2 file:py-1.5 file:px-3 file:rounded-lg file:border-0 file:text-xs file:font-semibold file:bg-cyan-600 file:text-white hover:file:bg-cyan-500 cursor-pointer">
        </div>

        <button type="submit" class="w-full py-2.5 rounded-xl font-bold bg-cyan-600 hover:bg-cyan-500 text-white transition">
          Record Expense & Deduct from Treasury
        </button>
      </form>
    </div>
  </div>

  <!-- MODAL 6: ROLLOVER TO NEXT MONTH -->
  <div id="modal-rollover" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-indigo-500/40 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative text-slate-100">
      <button onclick="closeModal('modal-rollover')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <div class="w-12 h-12 rounded-2xl bg-indigo-500/20 border border-indigo-500/40 mx-auto flex items-center justify-center text-indigo-400 mb-2">
        <i class="fa-solid fa-calendar-plus text-xl"></i>
      </div>
      <h3 class="text-base font-bold text-center text-white">Next Month Cycle Roll-Over</h3>
      <p class="text-xs text-slate-400 text-center mt-1">
        This automated engine will:
      </p>

      <div class="mt-3 p-3 bg-slate-800/70 rounded-xl border border-slate-700 text-xs space-y-1.5 text-slate-300">
        <div class="flex items-start gap-1.5">
          <span class="text-emerald-400 font-bold">✓</span>
          <span>Unpaid balance carries forward as next month's <strong>OLD BAL</strong>.</span>
        </div>
        <div class="flex items-start gap-1.5">
          <span class="text-emerald-400 font-bold">✓</span>
          <span>Current meter reading rolls into next month's <strong>PREV READING</strong>.</span>
        </div>
        <div class="flex items-start gap-1.5">
          <span class="text-emerald-400 font-bold">✓</span>
          <span>One-click cloud sync across all resident devices!</span>
        </div>
      </div>

      <div class="mt-4">
        <label class="block text-slate-300 text-xs font-medium mb-1">New Month Name</label>
        <input type="text" id="rollover-new-month-name" placeholder="e.g. September 2026" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2 text-xs text-amber-300 font-bold">
      </div>

      <div class="mt-4 flex gap-2">
        <button onclick="confirmRollover()" class="w-full py-2.5 bg-indigo-600 hover:bg-indigo-500 text-white font-bold rounded-xl text-xs transition">
          Execute Roll-Over Now
        </button>
      </div>
    </div>
  </div>

  <!-- MODAL 7: VIEW PROOF / VOUCHER IMAGE PREVIEW -->
  <div id="modal-image-preview" class="fixed inset-0 bg-black/90 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 border border-slate-700 rounded-3xl max-w-xl w-full p-5 shadow-2xl relative text-slate-100 max-h-[90vh] flex flex-col">
      <button onclick="closeModal('modal-image-preview')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800 z-10">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <h3 id="preview-image-title" class="text-sm font-bold text-white mb-2">Receipt Document Preview</h3>
      <div class="flex-1 overflow-auto flex items-center justify-center bg-slate-950 rounded-2xl p-2 border border-slate-800">
        <img id="preview-image-src" src="" alt="Receipt Proof" class="max-h-[70vh] object-contain rounded-lg">
      </div>
    </div>
  </div>

  <!-- MODAL 8: ITEMIZED PRINTABLE BILL SLIP -->
  <div id="modal-bill-slip" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 hidden flex items-center justify-center p-3 sm:p-4 overflow-y-auto">
    <div class="bg-slate-900 border border-amber-500/40 rounded-3xl max-w-lg w-full p-6 shadow-2xl relative text-slate-100 max-h-[95vh] overflow-y-auto">
      <button onclick="closeModal('modal-bill-slip')" class="absolute top-4 right-4 text-slate-400 hover:text-white p-2 rounded-xl bg-slate-800 no-print">
        <i class="fa-solid fa-xmark"></i>
      </button>

      <div id="printable-receipt" class="space-y-4">
        <!-- Header -->
        <div class="text-center border-b border-amber-500/30 pb-3">
          <div class="text-[10px] bg-amber-500/20 text-amber-300 px-3 py-0.5 rounded-full inline-block font-bold uppercase mb-1">
            Official Maintenance & Water Demand Slip
          </div>
          <h2 class="text-xl font-bold font-serif text-white">श्री जगन्नाथ अपार्टमेंट</h2>
          <p class="text-xs text-slate-300">Shree Jagannath Apartment RWA • Dwarka / Delhi NCR</p>
          <p class="text-[11px] text-amber-400 mt-0.5">Billing Month: <span id="slip-month">August 2026</span></p>
        </div>

        <!-- Resident Details -->
        <div class="bg-slate-800/80 p-3.5 rounded-xl border border-slate-700 grid grid-cols-2 gap-2 text-xs">
          <div>
            <span class="text-slate-400 block text-[10px]">Resident Name:</span>
            <span id="slip-name" class="font-bold text-white text-sm">SK Sharma</span>
          </div>
          <div>
            <span class="text-slate-400 block text-[10px]">Flat & Wing:</span>
            <span id="slip-flat-wing" class="font-bold text-amber-300 text-sm">G1 (Wing-A)</span>
          </div>
          <div>
            <span class="text-slate-400 block text-[10px]">Water Meter No:</span>
            <span id="slip-meter" class="font-mono text-slate-200">1440974</span>
          </div>
          <div>
            <span class="text-slate-400 block text-[10px]">Water Consumed:</span>
            <span id="slip-water-used" class="font-bold text-sky-300">5,910 Litres</span>
          </div>
        </div>

        <!-- Itemized Breakdown -->
        <div class="space-y-1.5 text-xs">
          <div class="font-bold text-slate-400 text-[11px] uppercase tracking-wider">Account Breakdown:</div>
          <div class="divide-y divide-slate-800 border-t border-b border-slate-800">
            <div class="flex justify-between py-1.5">
              <span>Net Water Charge (<span id="slip-water-rate-lbl">@₹0.15/L</span>):</span>
              <span id="slip-net-water" class="font-semibold text-slate-200">₹286.50</span>
            </div>
            <div class="flex justify-between py-1.5">
              <span>Society Maintenance Charge:</span>
              <span id="slip-maint" class="font-semibold text-slate-200">₹1,000.00</span>
            </div>
            <div class="flex justify-between py-1.5" id="slip-row-repair">
              <span>Electricity & Shaft Work:</span>
              <span id="slip-repairs" class="font-semibold text-slate-200">₹0.00</span>
            </div>
            <div class="flex justify-between py-1.5" id="slip-row-old">
              <span>Previous Arrears / Old Balance:</span>
              <span id="slip-old-bal" class="font-semibold text-rose-400">₹0.00</span>
            </div>
            <div class="flex justify-between py-1.5" id="slip-row-adv">
              <span>Advance Adjust / Need Adv:</span>
              <span id="slip-adv" class="font-semibold text-amber-400">₹0.00</span>
            </div>
          </div>

          <div class="bg-amber-500/20 p-3 rounded-xl border border-amber-500/40 flex justify-between items-center text-sm">
            <span class="font-bold text-amber-300">Total Demand Due:</span>
            <span id="slip-total-due" class="font-black text-amber-300 text-lg">₹1,287.00</span>
          </div>

          <div class="p-3 bg-emerald-950/30 rounded-xl border border-emerald-500/30 flex justify-between items-center text-xs">
            <div>
              <span class="text-slate-400 block text-[10px]">Payment Received:</span>
              <span id="slip-paid-amt" class="font-bold text-emerald-400">₹0.00</span>
            </div>
            <div class="text-right">
              <span class="text-slate-400 block text-[10px]">Balance Outstanding:</span>
              <span id="slip-balance-amt" class="font-bold text-rose-400">₹1,287.00</span>
            </div>
          </div>
        </div>

        <div class="pt-3 border-t border-slate-800 text-[10px] text-slate-400 flex justify-between items-end">
          <div>
            <p class="font-serif text-slate-300 font-bold">Shree Jagannath Apartment RWA</p>
            <p>Dwarka, New Delhi</p>
          </div>
          <div class="text-right">
            <p class="font-medium text-slate-300">Authorized Signatory / Secretary</p>
          </div>
        </div>
      </div>

      <div class="mt-4 flex gap-2 justify-end no-print">
        <button onclick="window.print()" class="px-4 py-2 bg-amber-500 hover:bg-amber-400 text-slate-950 font-bold text-xs rounded-xl transition flex items-center gap-1.5">
          <i class="fa-solid fa-print"></i>
          <span>Print Official Slip</span>
        </button>
      </div>
    </div>
  </div>

  <!-- TOAST NOTIFICATION -->
  <div id="toast" class="fixed bottom-6 right-6 z-50 bg-slate-900 border border-amber-500/50 text-white px-4 py-3 rounded-2xl shadow-2xl flex items-center gap-3 transform translate-y-24 opacity-0 transition-all duration-300 pointer-events-none text-xs sm:text-sm">
    <div class="text-amber-400">
      <i class="fa-solid fa-circle-check text-base"></i>
    </div>
    <span id="toast-message">Operation successful</span>
  </div>

  <!-- FIREBASE ES MODULES & REALTIME CLOUD INTEGRATION -->
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
    import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
    import { getFirestore, doc, getDoc, setDoc, updateDoc, onSnapshot, collection } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

    const STORAGE_KEY = 'SJA_MAINTENANCE_DB_REALTIME_V4';
    let currentRole = 'VIEWER'; // 'ADMIN' or 'VIEWER'
    let activeViewTab = 'BOTH';
    let currentMonthKey = '2026-08';
    let searchQuery = '';

    // Firebase Globals
    const appId = typeof __app_id !== 'undefined' ? __app_id : 'shree-jagannath-apt';
    let app, db, auth;
    let currentUser = null;
    let isCloudConnected = false;

    // Seed Data from Official August 2026 Maintenance Ledger
    const SEED_WING_A = [
      { id: "A-G1", wing: "WING-A", flat: "G1", name: "SK Sharma", meter: "1440974", prev: 89850, curr: 95760, used: 5910, adv: 1000, rate: 0.15, netWater: 286.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1287, paid: 0 },
      { id: "A-G2", wing: "WING-A", flat: "G2", name: "Nandan Singh Mehra", meter: "232407840", prev: 228400, curr: 238760, used: 10360, adv: 1000, rate: 0.15, netWater: 954.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1954, paid: 0 },
      { id: "A-G3", wing: "WING-A", flat: "G3", name: "Ajay Mishra", meter: "1396608", prev: 316200, curr: 332280, used: 16080, adv: 1280, rate: 0.15, netWater: 1812.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2812, paid: 0 },
      { id: "A-G5", wing: "WING-A", flat: "G5", name: "Anoj Gupta", meter: "1437351", prev: 143440, curr: 144220, used: 780, adv: 1000, rate: 0.15, netWater: 0.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1000, paid: 0 },
      { id: "A-A1", wing: "WING-A", flat: "A1", name: "Amit Soam", meter: "1432694", prev: 149060, curr: 157570, used: 8510, adv: 1000, rate: 0.15, netWater: 676.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1677, paid: 0 },
      { id: "A-A2", wing: "WING-A", flat: "A2", name: "Kanhaiya Kumar Jha", meter: "1396000", prev: 224500, curr: 226730, used: 2230, adv: 1800, rate: 0.15, netWater: 0.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1000, paid: 0 },
      { id: "A-A3", wing: "WING-A", flat: "A3", name: "Rajnish Kumar", meter: "1393412", prev: 163140, curr: 171340, used: 8200, adv: 500, rate: 0.15, netWater: 630.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1630, paid: 0 },
      { id: "A-A4", wing: "WING-A", flat: "A4", name: "Naresh Kumar", meter: "1396613", prev: 200080, curr: 206840, used: 6760, adv: 1000, rate: 0.15, netWater: 414.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1414, paid: 0 },
      { id: "A-A5", wing: "WING-A", flat: "A5", name: "Nitin Kumar Singh", meter: "1393408", prev: 216680, curr: 228550, used: 11870, adv: 724, rate: 0.15, netWater: 1180.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2181, paid: 0 },
      { id: "A-B1", wing: "WING-A", flat: "B1", name: "Jitender Pratap", meter: "232407837", prev: 187180, curr: 196660, used: 9480, adv: 1000, rate: 0.15, netWater: 822.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1822, paid: 0 },
      { id: "A-B2", wing: "WING-A", flat: "B2", name: "Indrajeet Singh", meter: "1416502", prev: 96840, curr: 104110, used: 7270, adv: 1226, rate: 0.15, netWater: 490.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1491, paid: 0 },
      { id: "A-B3", wing: "WING-A", flat: "B3", name: "Ashish Choutala", meter: "232407839", prev: 307880, curr: 317780, used: 9900, adv: 1721, rate: 0.15, netWater: 885.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1885, paid: 0 },
      { id: "A-B4", wing: "WING-A", flat: "B4", name: "Naresh Jeonwal", meter: "1440984", prev: 179250, curr: 188070, used: 8820, adv: 1000, rate: 0.15, netWater: 723.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1723, paid: 0 },
      { id: "A-B5", wing: "WING-A", flat: "B5", name: "Bindu", meter: "1396617", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 400, elec: 0, shaft: 0, oldBal: 3300, reqAdv: 0, needPay: 3700, paid: 0 },
      { id: "A-C1", wing: "WING-A", flat: "C1", name: "Aamir Khan/Aman", meter: "3052287", prev: 124340, curr: 127600, used: 3260, adv: 1000, rate: 0.15, netWater: 0.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1000, paid: 0 },
      { id: "A-C3", wing: "WING-A", flat: "C3", name: "Shailendra Kumar", meter: "1419801", prev: 296260, curr: 309280, used: 13020, adv: 975, rate: 0.15, netWater: 1353.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2353, paid: 0 },
      { id: "A-C4", wing: "WING-A", flat: "C4", name: "Atul Singh", meter: "1419802", prev: 136790, curr: 142410, used: 5620, adv: 586, rate: 0.15, netWater: 243.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1243, paid: 0 },
      { id: "A-C5", wing: "WING-A", flat: "C5", name: "Krishna Jha", meter: "1426421", prev: 110170, curr: 118070, used: 7900, adv: 1000, rate: 0.15, netWater: 585.00, maint: 1000, elec: 0, shaft: 0, oldBal: 1266, reqAdv: 0, needPay: 2851, paid: 0 },
      { id: "A-D1", wing: "WING-A", flat: "D1", name: "Rahul Verma", meter: "1419382", prev: 267240, curr: 279380, used: 12140, adv: 1445, rate: 0.15, netWater: 1221.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2221, paid: 0 },
      { id: "A-D2", wing: "WING-A", flat: "D2", name: "Indra Singh", meter: "1396601", prev: 266380, curr: 277050, used: 10670, adv: 1335, rate: 0.15, netWater: 1000.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2001, paid: 0 },
      { id: "A-D3", wing: "WING-A", flat: "D3", name: "Chandan Tiwari", meter: "1426412", prev: 96220, curr: 100460, used: 4240, adv: 902, rate: 0.15, netWater: 36.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1036, paid: 0 },
      { id: "A-D4", wing: "WING-A", flat: "D4", name: "Pawan Modi", meter: "1440979", prev: 85990, curr: 91050, used: 5060, adv: 912, rate: 0.15, netWater: 159.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1159, paid: 0 },
      { id: "A-D5", wing: "WING-A", flat: "D5", name: "Karan Singh", meter: "1426407", prev: 135640, curr: 142950, used: 7310, adv: 824, rate: 0.15, netWater: 496.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1497, paid: 0 },
      { id: "A-E1", wing: "WING-A", flat: "E1", name: "Rajni Verma", meter: "1419391", prev: 208400, curr: 217650, used: 9250, adv: 1200, rate: 0.15, netWater: 787.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1788, paid: 0 },
      { id: "A-E4", wing: "WING-A", flat: "E4", name: "E4", meter: "99030", prev: 99030, curr: 104760, used: 5730, adv: 1000, rate: 0.15, netWater: 259.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1260, paid: 0 },
      { id: "A-E3", wing: "WING-A", flat: "E-3", name: "E-3", meter: "99040", prev: 99040, curr: 108260, used: 9220, adv: 1000, rate: 0.15, netWater: 783.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1783, paid: 0 },
      { id: "A-E5", wing: "WING-A", flat: "E-5", name: "E-5", meter: "1393407", prev: 89290, curr: 100440, used: 11150, adv: 1000, rate: 0.15, netWater: 1072.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2073, paid: 0 }
    ];

    const SEED_WING_B = [
      { id: "B-G1", wing: "WING-B", flat: "G/1", name: "G1", meter: "N/A", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 1000, oldBal: 0, reqAdv: 0, needPay: 2040, paid: 0 },
      { id: "B-G5", wing: "WING-B", flat: "G/5", name: "G/5", meter: "N/A", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 400, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 400, paid: 0 },
      { id: "B-G3", wing: "WING-B", flat: "G3", name: "Mamta Dager", meter: "N/A", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1040, paid: 0 },
      { id: "B-G2", wing: "WING-B", flat: "G2", name: "Mahira Khan", meter: "1389051", prev: 72800, curr: 78050, used: 5250, adv: 1002, rate: 0.15, netWater: 187.50, maint: 1000, elec: 1040, shaft: 1000, oldBal: 2918, reqAdv: 0, needPay: 6145.5, paid: 0 },
      { id: "B-G4", wing: "WING-B", flat: "G4", name: "Deepak Sah", meter: "232407814", prev: 162990, curr: 170360, used: 7370, adv: 868, rate: 0.15, netWater: 505.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1505.5, paid: 0 },
      { id: "B-A1", wing: "WING-B", flat: "A1", name: "Kamla Devi", meter: "232417697", prev: 191450, curr: 203600, used: 12150, adv: 1000, rate: 0.15, netWater: 1222.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2222.5, paid: 0 },
      { id: "B-A2", wing: "WING-B", flat: "A2", name: "Maheswar Prasad Singh", meter: "1420841", prev: 251150, curr: 262250, used: 11100, adv: 1200, rate: 0.15, netWater: 1065.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2065, paid: 0 },
      { id: "B-A3", wing: "WING-B", flat: "A3", name: "PRAKASH KUMAR", meter: "232416100", prev: 154800, curr: 160060, used: 5260, adv: 600, rate: 0.15, netWater: 189.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1189, paid: 0 },
      { id: "B-A4", wing: "WING-B", flat: "A4", name: "Sujaan Singh", meter: "1433890", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1040, paid: 0 },
      { id: "B-A5", wing: "WING-B", flat: "A5", name: "Vishnu Tiwari", meter: "1419384", prev: 187880, curr: 194440, used: 6560, adv: 1144, rate: 0.15, netWater: 384.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1384, paid: 0 },
      { id: "B-A6", wing: "WING-B", flat: "A6", name: "Sumeet Shah", meter: "1424581", prev: 145990, curr: 157820, used: 11830, adv: 0, rate: 0.15, netWater: 1174.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 1000, needPay: 3174.5, paid: 0 },
      { id: "B-B1", wing: "WING-B", flat: "B1", name: "Sunita/Harendar Gujjar", meter: "1419790", prev: 302520, curr: 311390, used: 8870, adv: 1530, rate: 0.15, netWater: 730.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1730.5, paid: 0 },
      { id: "B-B2", wing: "WING-B", flat: "B2", name: "Anil Kumar", meter: "232407834", prev: 212500, curr: 221960, used: 9460, adv: 1098, rate: 0.15, netWater: 819.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1819, paid: 0 },
      { id: "B-B3", wing: "WING-B", flat: "B3", name: "Prakash Arya", meter: "1393411", prev: 213080, curr: 220040, used: 6960, adv: 1200, rate: 0.15, netWater: 444.00, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1444, paid: 0 },
      { id: "B-B4", wing: "WING-B", flat: "B4", name: "Ravishanker Singh", meter: "232407820", prev: 250970, curr: 258660, used: 7690, adv: 1003, rate: 0.15, netWater: 553.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1553.5, paid: 0 },
      { id: "B-B5", wing: "WING-B", flat: "B5", name: "Harpreet Singh", meter: "1419796", prev: 171780, curr: 173640, used: 1860, adv: 1001, rate: 0.15, netWater: 0.00, maint: 1000, elec: 1040, shaft: 0, oldBal: 902, reqAdv: 0, needPay: 2942, paid: 0 },
      { id: "B-B6", wing: "WING-B", flat: "B/6", name: "B/6", meter: "90110", prev: 90110, curr: 106150, used: 16040, adv: 0, rate: 0.15, netWater: 1806.00, maint: 1000, elec: 1040, shaft: 2000, oldBal: 3515, reqAdv: 2000, needPay: 10361, paid: 0 },
      { id: "B-C1", wing: "WING-B", flat: "C1", name: "Rajesh Kumar", meter: "1420846", prev: 325510, curr: 337500, used: 11990, adv: 2000, rate: 0.15, netWater: 1198.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2198.5, paid: 0 },
      { id: "B-C2", wing: "WING-B", flat: "C2", name: "Chandan Rautela", meter: "1419813", prev: 218600, curr: 227730, used: 9130, adv: 1446, rate: 0.15, netWater: 769.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1769.5, paid: 0 },
      { id: "B-C3", wing: "WING-B", flat: "C3", name: "Mahendra Aswal", meter: "1424572", prev: 171150, curr: 177800, used: 6650, adv: 898, rate: 0.15, netWater: 397.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1397.5, paid: 0 },
      { id: "B-C4", wing: "WING-B", flat: "C4", name: "Akbar Ali", meter: "N/A", prev: 78550, curr: 82750, used: 4200, adv: 706, rate: 0.15, netWater: 30.00, maint: 1000, elec: 1040, shaft: 1000, oldBal: 0, reqAdv: 0, needPay: 3070, paid: 0 },
      { id: "B-C5", wing: "WING-B", flat: "C5", name: "Aman Rana", meter: "1433865", prev: 85030, curr: 92660, used: 7630, adv: 600, rate: 0.15, netWater: 544.50, maint: 1000, elec: 0, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 1544.5, paid: 0 },
      { id: "B-C6", wing: "WING-B", flat: "C6", name: "Rahul Mishra", meter: "1432592", prev: 200610, curr: 200610, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 1000, oldBal: 5562, reqAdv: 0, needPay: 7602, paid: 0 },
      { id: "B-D1", wing: "WING-B", flat: "D1", name: "NISHANT", meter: "1419383", prev: 291430, curr: 302990, used: 11560, adv: 0, rate: 0.15, netWater: 1134.00, maint: 1000, elec: 1040, shaft: 1000, oldBal: 4326, reqAdv: 1000, needPay: 9602, paid: 0 },
      { id: "B-D2", wing: "WING-B", flat: "D/2", name: "Garima", meter: "N/A", prev: 29550, curr: 38530, used: 8980, adv: 0, rate: 0.15, netWater: 747.00, maint: 1000, elec: 1040, shaft: 1000, oldBal: 6823, reqAdv: 1000, needPay: 11610, paid: 0 },
      { id: "B-D3", wing: "WING-B", flat: "D3", name: "Erdward Kujur", meter: "1419803", prev: 178900, curr: 185670, used: 6770, adv: 1118, rate: 0.15, netWater: 415.50, maint: 1000, elec: 1040, shaft: 0, oldBal: 0, reqAdv: 0, needPay: 2455.5, paid: 0 },
      { id: "B-D4", wing: "WING-B", flat: "D4", name: "Badal", meter: "1415963", prev: 125320, curr: 134710, used: 9390, adv: 156, rate: 0.15, netWater: 808.50, maint: 1000, elec: 0, shaft: 0, oldBal: 3157, reqAdv: 1000, needPay: 5965.5, paid: 0 },
      { id: "B-D5", wing: "WING-B", flat: "D/5", name: "D/5", meter: "N/A", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 1000, oldBal: 0, reqAdv: 0, needPay: 2040, paid: 0 },
      { id: "B-D6", wing: "WING-B", flat: "D/6", name: "D/6", meter: "N/A", prev: 0, curr: 0, used: 0, adv: 0, rate: 0.15, netWater: 0.00, maint: 0, elec: 1040, shaft: 1000, oldBal: 0, reqAdv: 0, needPay: 2040, paid: 0 }
    ];

    let dbState = null;

    function createInitialState() {
      return {
        settings: {
          adminMobile: '7053600701',
          adminPassword: '7053600701',
          upiId: '7053600701@upi',
          qrImage: ''
        },
        months: {
          '2026-08': {
            name: 'August 2026',
            waterRate: 0.15,
            wingA: JSON.parse(JSON.stringify(SEED_WING_A)),
            wingB: JSON.parse(JSON.stringify(SEED_WING_B)),
            expenses: [
              { id: 'exp-1', title: 'Main Borewell Motor Servicing', category: 'Water Motor', amount: 3500, date: '2026-08-15', vendor: 'Shree Balaji Electricals', voucher: '' },
              { id: 'exp-2', title: 'Water Tanker Supply (5000L Emergency)', category: 'Water Tanker', amount: 1600, date: '2026-08-18', vendor: 'Balaji Water Suppliers', voucher: '' },
              { id: 'exp-3', title: 'Building Security Guard Salary (Adv)', category: 'Staff/Guard', amount: 12000, date: '2026-08-20', vendor: 'Security Agency', voucher: '' }
            ],
            paymentProofs: []
          }
        }
      };
    }

    async function initCloudSync() {
      const cached = localStorage.getItem(STORAGE_KEY);
      if (cached) {
        try { dbState = JSON.parse(cached); } catch(e) { dbState = createInitialState(); }
      } else {
        dbState = createInitialState();
      }

      // Check for environment Firebase config
      try {
        if (typeof __firebase_config !== 'undefined') {
          const firebaseConfig = JSON.parse(__firebase_config);
          app = initializeApp(firebaseConfig);
          db = getFirestore(app);
          auth = getAuth(app);

          if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
            await signInWithCustomToken(auth, __initial_auth_token);
          } else {
            await signInAnonymously(auth);
          }

          currentUser = auth.currentUser;
          isCloudConnected = true;

          // RULE 1: Subscribe to public cloud document for settings and current month
          const settingsRef = doc(db, 'artifacts', appId, 'public', 'data', 'society_settings', 'main');
          onSnapshot(settingsRef, (snap) => {
            if (snap.exists()) {
              dbState.settings = { ...dbState.settings, ...snap.data() };
              saveLocalCache();
              updateQrDisplay();
            } else {
              setDoc(settingsRef, dbState.settings).catch(console.error);
            }
          }, (err) => console.warn("Settings sync notice:", err));

          // Subscribe to Month Document
          subscribeToMonthCloud(currentMonthKey);
          updateSyncUI(true);
        } else {
          updateSyncUI(false);
        }
      } catch (err) {
        console.warn("Cloud connection notice:", err);
        updateSyncUI(false);
      }
    }

    function subscribeToMonthCloud(mKey) {
      if (!isCloudConnected || !db) return;
      const monthRef = doc(db, 'artifacts', appId, 'public', 'data', 'society_months', mKey);
      onSnapshot(monthRef, (snap) => {
        if (snap.exists()) {
          dbState.months[mKey] = snap.data();
          saveLocalCache();
          refreshAllViews();
        } else {
          if (dbState.months[mKey]) {
            setDoc(monthRef, dbState.months[mKey]).catch(console.error);
          }
        }
      }, (err) => console.warn("Month sync error:", err));
    }

    function saveLocalCache() {
      try {
        localStorage.setItem(STORAGE_KEY, JSON.stringify(dbState));
      } catch (e) {
        console.warn("Storage warning:", e);
      }
    }

    async function pushCurrentMonthToCloud() {
      saveLocalCache();
      if (!isCloudConnected || !db || !auth.currentUser) return;
      try {
        const monthRef = doc(db, 'artifacts', appId, 'public', 'data', 'society_months', currentMonthKey);
        await setDoc(monthRef, dbState.months[currentMonthKey]);
      } catch (err) {
        console.error("Cloud push failed:", err);
      }
    }

    async function pushSettingsToCloud() {
      saveLocalCache();
      if (!isCloudConnected || !db || !auth.currentUser) return;
      try {
        const settingsRef = doc(db, 'artifacts', appId, 'public', 'data', 'society_settings', 'main');
        await setDoc(settingsRef, dbState.settings);
      } catch (err) {
        console.error("Settings push failed:", err);
      }
    }

    function updateSyncUI(online) {
      const el = document.getElementById('sync-status-indicator');
      if (online) {
        el.className = "text-[11px] px-2 py-0.5 rounded-full bg-emerald-950/60 text-emerald-300 border border-emerald-500/30 flex items-center gap-1";
        el.innerHTML = '<i class="fa-solid fa-cloud-arrow-up text-[10px]"></i> Live Sync Active';
      } else {
        el.className = "text-[11px] px-2 py-0.5 rounded-full bg-slate-800 text-slate-300 border border-slate-600 flex items-center gap-1";
        el.innerHTML = '<i class="fa-solid fa-database text-[10px]"></i> Local Cache Mode';
      }
    }

    function getCurrentMonth() {
      if (!dbState.months[currentMonthKey]) {
        currentMonthKey = Object.keys(dbState.months)[0];
      }
      return dbState.months[currentMonthKey];
    }

    function calculateMasterMetrics() {
      const month = getCurrentMonth();
      const currentRate = month.waterRate !== undefined ? month.waterRate : 0.15;
      document.getElementById('banner-water-rate').textContent = `₹${currentRate}/L`;
      document.getElementById('btn-curr-rate').textContent = `₹${currentRate}`;
      
      let billedWingA = 0, paidWingA = 0, waterLitresA = 0, netWaterA = 0;
      (month.wingA || []).forEach(f => {
        billedWingA += Number(f.needPay || 0);
        paidWingA += Number(f.paid || 0);
        waterLitresA += Number(f.used || 0);
        netWaterA += Number(f.netWater || 0);
      });

      let billedWingB = 0, paidWingB = 0, waterLitresB = 0, netWaterB = 0;
      (month.wingB || []).forEach(f => {
        billedWingB += Number(f.needPay || 0);
        paidWingB += Number(f.paid || 0);
        waterLitresB += Number(f.used || 0);
        netWaterB += Number(f.netWater || 0);
      });

      const totalBilled = billedWingA + billedWingB;
      const totalPaid = paidWingA + paidWingB;
      const totalPending = Math.max(0, totalBilled - totalPaid);

      let totalExpenses = 0;
      (month.expenses || []).forEach(e => totalExpenses += Number(e.amount || 0));

      const netFund = totalPaid - totalExpenses;

      // Update Master KPI Badges
      document.getElementById('stat-total-billed').textContent = `₹${totalBilled.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('stat-total-received').textContent = `₹${totalPaid.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('stat-total-pending').textContent = `₹${totalPending.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('stat-total-expense').textContent = `₹${totalExpenses.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('stat-net-fund').textContent = `₹${netFund.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;

      const recoveryPercent = totalBilled > 0 ? Math.round((totalPaid / totalBilled) * 100) : 0;
      document.getElementById('stat-collection-rate').textContent = `${recoveryPercent}% Recovered`;

      // Update Dedicated Wing A Box Metrics
      document.getElementById('wing-a-water-used').textContent = `${waterLitresA.toLocaleString()} L`;
      document.getElementById('wing-a-net-water').textContent = `₹${netWaterA.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('wing-a-demand').textContent = `₹${billedWingA.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('wing-a-pending').textContent = `₹${Math.max(0, billedWingA - paidWingA).toLocaleString('en-IN', {minimumFractionDigits: 2})}`;

      // Update Dedicated Wing B Box Metrics
      document.getElementById('wing-b-water-used').textContent = `${waterLitresB.toLocaleString()} L`;
      document.getElementById('wing-b-net-water').textContent = `₹${netWaterB.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('wing-b-demand').textContent = `₹${billedWingB.toLocaleString('en-IN', {minimumFractionDigits: 2})}`;
      document.getElementById('wing-b-pending').textContent = `₹${Math.max(0, billedWingB - paidWingB).toLocaleString('en-IN', {minimumFractionDigits: 2})}`;

      // Badges
      document.getElementById('expense-count-badge').textContent = (month.expenses || []).length;
      document.getElementById('proofs-badge').textContent = (month.paymentProofs || []).length;
    }

    function renderWingTable(tbodyId, dataList, isWingA) {
      const tbody = document.getElementById(tbodyId);
      const q = searchQuery.toLowerCase().trim();

      const filtered = (dataList || []).filter(item => {
        if (!q) return true;
        return item.flat.toLowerCase().includes(q) ||
               item.name.toLowerCase().includes(q) ||
               item.meter.toLowerCase().includes(q);
      });

      if (filtered.length === 0) {
        tbody.innerHTML = `<tr><td colspan="15" class="py-8 text-center text-slate-500">No flats found matching criteria.</td></tr>`;
        return;
      }

      tbody.innerHTML = filtered.map(row => {
        const paid = Number(row.paid || 0);
        const due = Number(row.needPay || 0);
        const bal = Math.max(0, due - paid);

        let statusBadge = '';
        if (paid >= due && due > 0) {
          statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/40">PAID</span>`;
        } else if (paid > 0) {
          statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-bold bg-amber-500/20 text-amber-300 border border-amber-500/40">PARTIAL</span>`;
        } else {
          statusBadge = `<span class="px-2 py-0.5 rounded text-[10px] font-bold bg-rose-500/20 text-rose-300 border border-rose-500/40">DUE</span>`;
        }

        // Special Work Badges with Highlighting (Electricity ₹1,040, Shaft ₹1,000 / ₹2,000)
        let specialWorkCell = '';
        if (!isWingA) {
          const elecBadge = row.elec > 0 
            ? `<span class="inline-flex items-center gap-1 px-1.5 py-0.5 rounded bg-amber-500/25 text-amber-300 font-bold border border-amber-500/50 text-[10px] glow-warning" title="Electricity Work Pending"><i class="fa-solid fa-bolt text-[9px] text-amber-400"></i>₹${row.elec}</span>`
            : '';
          const shaftBadge = row.shaft > 0
            ? `<span class="inline-flex items-center gap-1 px-1.5 py-0.5 rounded bg-purple-500/25 text-purple-300 font-bold border border-purple-500/50 text-[10px] glow-warning" title="Shaft Repair Pending"><i class="fa-solid fa-wrench text-[9px] text-purple-400"></i>₹${row.shaft}</span>`
            : '';
          
          if (!elecBadge && !shaftBadge) {
            specialWorkCell = `<td class="py-2.5 px-2 text-center text-slate-500">—</td>`;
          } else {
            specialWorkCell = `<td class="py-2.5 px-2 text-center"><div class="flex flex-wrap items-center justify-center gap-1">${elecBadge}${shaftBadge}</div></td>`;
          }
        }

        // Action Buttons: Viewers get Slip; Admin gets Edit
        let actions = `
          <button onclick="window.appActions.openSlip('${row.id}')" class="px-2 py-1 text-[11px] rounded-lg bg-amber-500/15 hover:bg-amber-500/30 text-amber-300 border border-amber-500/30 font-semibold" title="View Printable Invoice">
            <i class="fa-solid fa-receipt mr-1"></i>Slip
          </button>
        `;

        if (currentRole === 'ADMIN') {
          actions += `
            <button onclick="window.appActions.openEditFlat('${row.id}')" class="px-2 py-1 text-[11px] rounded-lg bg-sky-500/20 hover:bg-sky-500/35 text-sky-300 border border-sky-500/40 font-bold" title="Edit Readings / Payments">
              <i class="fa-solid fa-pen-to-square"></i>
            </button>
          `;
        }

        return `
          <tr class="hover:bg-slate-800/40 transition">
            <td class="py-2.5 px-3 text-center font-extrabold text-amber-400 font-mono text-xs">${row.flat}</td>
            <td class="py-2.5 px-3">
              <div class="font-semibold text-slate-200">${row.name}</div>
            </td>
            <td class="py-2.5 px-2 text-center font-mono text-slate-400 text-[11px]">${row.meter}</td>
            <td class="py-2.5 px-2 text-right font-mono text-slate-400">${row.prev ? row.prev.toLocaleString() : '—'}</td>
            <td class="py-2.5 px-2 text-right font-mono text-slate-300">${row.curr ? row.curr.toLocaleString() : '—'}</td>
            <td class="py-2.5 px-3 text-right font-mono font-bold text-sky-300">${row.used ? row.used.toLocaleString() + ' L' : '0 L'}</td>
            <td class="py-2.5 px-2 text-right font-mono text-slate-300">₹${Number(row.netWater || 0).toFixed(2)}</td>
            <td class="py-2.5 px-2 text-right font-mono text-slate-300">₹${row.maint}</td>
            ${specialWorkCell}
            <td class="py-2.5 px-2 text-right font-mono ${row.oldBal > 0 ? 'text-rose-400 font-semibold' : 'text-slate-500'}">
              ${row.oldBal > 0 ? '₹' + Number(row.oldBal).toLocaleString() : '—'}
            </td>
            <td class="py-2.5 px-3 text-right font-mono font-extrabold text-amber-300 bg-amber-500/5">₹${due.toLocaleString()}</td>
            <td class="py-2.5 px-3 text-right font-mono font-bold text-emerald-400 bg-emerald-500/5">₹${paid.toLocaleString()}</td>
            <td class="py-2.5 px-3 text-right font-mono font-extrabold ${bal > 0 ? 'text-rose-400' : 'text-slate-500'} bg-rose-500/5">₹${bal.toLocaleString()}</td>
            <td class="py-2.5 px-2 text-center">${statusBadge}</td>
            <td class="py-2.5 px-3 text-center">
              <div class="flex items-center justify-center gap-1.5">${actions}</div>
            </td>
          </tr>
        `;
      }).join('');
    }

    function renderExpensesTable() {
      const tbody = document.getElementById('expenses-table-body');
      const month = getCurrentMonth();
      const expenses = month.expenses || [];

      if (expenses.length === 0) {
        tbody.innerHTML = `<tr><td colspan="7" class="py-8 text-center text-slate-500">No society expenses recorded for this month yet.</td></tr>`;
        return;
      }

      tbody.innerHTML = expenses.map(exp => {
        const voucherBtn = exp.voucher 
          ? `<button onclick="window.appActions.previewImage('${exp.voucher}', '${exp.title} Voucher')" class="px-2.5 py-1 text-xs bg-cyan-500/20 text-cyan-300 rounded-lg border border-cyan-500/40 hover:bg-cyan-500/30 font-semibold"><i class="fa-solid fa-file-image mr-1"></i>View Bill</button>`
          : `<span class="text-slate-500 text-xs">No Bill</span>`;

        const deleteBtn = (currentRole === 'ADMIN')
          ? `<button onclick="window.appActions.deleteExpense('${exp.id}')" class="text-rose-400 hover:text-rose-300 p-1" title="Delete"><i class="fa-solid fa-trash-can"></i></button>`
          : '';

        return `
          <tr class="hover:bg-slate-800/40 transition">
            <td class="py-3 px-4 font-mono text-slate-300">${exp.date}</td>
            <td class="py-3 px-4 font-semibold text-slate-100">${exp.title}</td>
            <td class="py-3 px-3"><span class="px-2 py-0.5 rounded text-[11px] bg-slate-800 border border-slate-700 text-slate-300">${exp.category}</span></td>
            <td class="py-3 px-3 text-slate-300">${exp.vendor}</td>
            <td class="py-3 px-3 text-right font-mono font-bold text-cyan-300">₹${Number(exp.amount).toLocaleString()}</td>
            <td class="py-3 px-3 text-center">${voucherBtn}</td>
            <td class="py-3 px-3 text-center">${deleteBtn}</td>
          </tr>
        `;
      }).join('');
    }

    function renderProofsTable() {
      const tbody = document.getElementById('proofs-table-body');
      const month = getCurrentMonth();
      const proofs = month.paymentProofs || [];

      if (proofs.length === 0) {
        tbody.innerHTML = `<tr><td colspan="8" class="py-8 text-center text-slate-500">No resident payment receipts waiting in queue.</td></tr>`;
        return;
      }

      tbody.innerHTML = proofs.map(p => {
        const receiptBtn = p.image 
          ? `<button onclick="window.appActions.previewImage('${p.image}', 'Payment Proof Flat ${p.flat}')" class="px-2.5 py-1 text-xs bg-amber-500/20 text-amber-300 rounded-lg border border-amber-500/40 hover:bg-amber-500/30 font-semibold"><i class="fa-solid fa-image mr-1"></i>View Slip</button>`
          : `<span class="text-slate-500 text-xs">No Image</span>`;

        const statusTag = p.status === 'APPROVED'
          ? `<span class="px-2 py-0.5 rounded text-[10px] font-bold bg-emerald-500/20 text-emerald-300 border border-emerald-500/40">APPROVED</span>`
          : `<span class="px-2 py-0.5 rounded text-[10px] font-bold bg-amber-500/20 text-amber-300 border border-amber-500/40">PENDING</span>`;

        const actionBtns = (currentRole === 'ADMIN' && p.status === 'PENDING')
          ? `<button onclick="window.appActions.approveProof('${p.id}')" class="px-3 py-1 bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold rounded-lg text-xs shadow"><i class="fa-solid fa-check mr-1"></i>Approve & Credit</button>`
          : `<span class="text-slate-500 text-xs">—</span>`;

        return `
          <tr class="hover:bg-slate-800/40 transition">
            <td class="py-3 px-3 font-mono text-slate-300">${p.date}</td>
            <td class="py-3 px-3 font-bold text-amber-400 font-mono">${p.flat} (${p.wing})</td>
            <td class="py-3 px-3 font-semibold text-slate-200">${p.name}</td>
            <td class="py-3 px-3 font-mono font-bold text-emerald-400">₹${Number(p.amount).toLocaleString()}</td>
            <td class="py-3 px-3 font-mono text-slate-300">${p.utr}</td>
            <td class="py-3 px-3 text-center">${receiptBtn}</td>
            <td class="py-3 px-3 text-center">${statusTag}</td>
            <td class="py-3 px-3 text-center">${actionBtns}</td>
          </tr>
        `;
      }).join('');
    }

    function refreshAllViews() {
      calculateMasterMetrics();
      const month = getCurrentMonth();
      renderWingTable('table-wing-a-body', month.wingA, true);
      renderWingTable('table-wing-b-body', month.wingB, false);
      renderExpensesTable();
      renderProofsTable();
      populateProofSelect();
      renderMonthSelectors();
    }

    function renderMonthSelectors() {
      const dSelect = document.getElementById('desktop-month-select');
      const mSelect = document.getElementById('mobile-month-select');
      
      const options = Object.keys(dbState.months).map(key => {
        return `<option value="${key}" ${key === currentMonthKey ? 'selected' : ''}>${dbState.months[key].name}</option>`;
      }).join('');

      dSelect.innerHTML = options;
      mSelect.innerHTML = options;
      document.getElementById('banner-month-name').textContent = dbState.months[currentMonthKey]?.name || currentMonthKey;
    }

    function switchMonth(key) {
      currentMonthKey = key;
      renderMonthSelectors();
      subscribeToMonthCloud(key);
      refreshAllViews();
      showToast(`Switched cycle to ${dbState.months[key]?.name}`);
    }

    function populateProofSelect() {
      const sel = document.getElementById('proof-flat-select');
      const month = getCurrentMonth();
      const all = [...(month.wingA || []), ...(month.wingB || [])];

      sel.innerHTML = all.map(f => {
        return `<option value="${f.id}">${f.flat} — ${f.name} (${f.wing})</option>`;
      }).join('');
    }

    function updateRoleUI() {
      const badge = document.getElementById('role-badge');
      const authBtnText = document.getElementById('admin-btn-text');
      const authBtnIcon = document.getElementById('admin-btn-icon');
      const rolloverBtn = document.getElementById('admin-rollover-btn');
      const adminQrControls = document.getElementById('admin-qr-controls');
      const changePassBtn = document.getElementById('admin-change-pwd-btn');
      const rateBtn = document.getElementById('admin-rate-btn');

      if (currentRole === 'ADMIN') {
        badge.innerHTML = '<i class="fa-solid fa-user-shield text-[9px] mr-1"></i> Admin Mode';
        badge.className = 'text-[10px] bg-amber-500/20 text-amber-300 font-sans px-2.5 py-0.5 rounded-full border border-amber-500/40 font-bold';
        authBtnText.textContent = 'Logout Admin';
        authBtnIcon.className = 'fa-solid fa-right-from-bracket text-slate-950';
        rolloverBtn.classList.remove('hidden');
        adminQrControls.classList.remove('hidden');
        changePassBtn.classList.remove('hidden');
        changePassBtn.classList.add('flex');
        rateBtn.classList.remove('hidden');
        rateBtn.classList.add('flex');
      } else {
        badge.innerHTML = '<i class="fa-solid fa-eye text-[9px] mr-1"></i> Viewer Mode';
        badge.className = 'text-[10px] bg-slate-800 text-slate-300 font-sans px-2.5 py-0.5 rounded-full border border-slate-600 font-semibold';
        authBtnText.textContent = 'Admin Login';
        authBtnIcon.className = 'fa-solid fa-lock text-slate-950';
        rolloverBtn.classList.add('hidden');
        adminQrControls.classList.add('hidden');
        changePassBtn.classList.add('hidden');
        changePassBtn.classList.remove('flex');
        rateBtn.classList.add('hidden');
        rateBtn.classList.remove('flex');
      }
      refreshAllViews();
    }

    window.appActions = {
      openSlip(flatId) {
        const month = getCurrentMonth();
        const flatObj = [...(month.wingA || []), ...(month.wingB || [])].find(f => f.id === flatId);
        if (!flatObj) return;

        const rate = month.waterRate !== undefined ? month.waterRate : 0.15;
        document.getElementById('slip-month').textContent = month.name;
        document.getElementById('slip-name').textContent = flatObj.name;
        document.getElementById('slip-flat-wing').textContent = `${flatObj.flat} (${flatObj.wing})`;
        document.getElementById('slip-meter').textContent = flatObj.meter || 'N/A';
        document.getElementById('slip-water-used').textContent = `${Number(flatObj.used || 0).toLocaleString()} Litres`;
        document.getElementById('slip-water-rate-lbl').textContent = `@₹${rate}/L`;
        document.getElementById('slip-net-water').textContent = `₹${Number(flatObj.netWater || 0).toFixed(2)}`;
        document.getElementById('slip-maint').textContent = `₹${flatObj.maint}`;

        const repairRow = document.getElementById('slip-row-repair');
        const repairAmt = Number(flatObj.elec || 0) + Number(flatObj.shaft || 0);
        if (repairAmt > 0) {
          repairRow.style.display = 'flex';
          document.getElementById('slip-repairs').textContent = `₹${repairAmt}`;
        } else {
          repairRow.style.display = 'none';
        }

        const oldRow = document.getElementById('slip-row-old');
        if (Number(flatObj.oldBal || 0) > 0) {
          oldRow.style.display = 'flex';
          document.getElementById('slip-old-bal').textContent = `₹${flatObj.oldBal}`;
        } else {
          oldRow.style.display = 'none';
        }

        const advRow = document.getElementById('slip-row-adv');
        if (Number(flatObj.reqAdv || 0) > 0) {
          advRow.style.display = 'flex';
          document.getElementById('slip-adv').textContent = `₹${flatObj.reqAdv}`;
        } else {
          advRow.style.display = 'none';
        }

        document.getElementById('slip-total-due').textContent = `₹${Number(flatObj.needPay).toLocaleString()}`;
        document.getElementById('slip-paid-amt').textContent = `₹${Number(flatObj.paid || 0).toLocaleString()}`;
        const bal = Math.max(0, flatObj.needPay - (flatObj.paid || 0));
        document.getElementById('slip-balance-amt').textContent = `₹${bal.toLocaleString()}`;

        openModal('modal-bill-slip');
      },

      openEditFlat(flatId) {
        if (currentRole !== 'ADMIN') return;
        const month = getCurrentMonth();
        const flatObj = [...(month.wingA || []), ...(month.wingB || [])].find(f => f.id === flatId);
        if (!flatObj) return;

        document.getElementById('edit-flat-id').value = flatObj.id;
        document.getElementById('edit-flat-subtitle').textContent = `Editing: ${flatObj.flat} (${flatObj.name}) - ${flatObj.wing}`;
        document.getElementById('edit-flat-name').value = flatObj.name;
        document.getElementById('edit-flat-meter').value = flatObj.meter || '';
        document.getElementById('edit-flat-prev').value = flatObj.prev || 0;
        document.getElementById('edit-flat-curr').value = flatObj.curr || 0;
        document.getElementById('edit-flat-adv').value = flatObj.adv || 0;
        document.getElementById('edit-flat-rate').value = flatObj.rate || month.waterRate || 0.15;
        document.getElementById('edit-flat-maint').value = flatObj.maint || 0;
        document.getElementById('edit-flat-elec').value = flatObj.elec || 0;
        document.getElementById('edit-flat-shaft').value = flatObj.shaft || 0;
        document.getElementById('edit-flat-oldbal').value = flatObj.oldBal || 0;
        document.getElementById('edit-flat-needpay').value = flatObj.needPay || 0;
        document.getElementById('edit-flat-paid').value = flatObj.paid || 0;

        openModal('modal-edit-flat');
      },

      deleteExpense(expId) {
        if (currentRole !== 'ADMIN') return;
        const month = getCurrentMonth();
        month.expenses = (month.expenses || []).filter(e => e.id !== expId);
        pushCurrentMonthToCloud();
        refreshAllViews();
        showToast("Expense removed from records.");
      },

      previewImage(src, title) {
        document.getElementById('preview-image-src').src = src;
        document.getElementById('preview-image-title').textContent = title || "Document Preview";
        openModal('modal-image-preview');
      },

      async approveProof(proofId) {
        if (currentRole !== 'ADMIN') return;
        const month = getCurrentMonth();
        const p = (month.paymentProofs || []).find(x => x.id === proofId);
        if (!p) return;

        p.status = 'APPROVED';
        const flatObj = (month.wingA || []).find(f => f.id === p.flatId) || (month.wingB || []).find(f => f.id === p.flatId);
        if (flatObj) {
          flatObj.paid = (Number(flatObj.paid) || 0) + Number(p.amount);
        }

        await pushCurrentMonthToCloud();
        refreshAllViews();
        showToast(`Approved ₹${p.amount} for Flat ${p.flat}! Account credited in real time.`);
      }
    };

    window.openWaterRateModal = function() {
      if (currentRole !== 'ADMIN') return;
      const month = getCurrentMonth();
      document.getElementById('input-new-water-rate').value = month.waterRate !== undefined ? month.waterRate : 0.15;
      openModal('modal-water-rate');
    };

    window.submitWaterRateChange = async function(e) {
      e.preventDefault();
      const newRate = parseFloat(document.getElementById('input-new-water-rate').value) || 0.15;
      const month = getCurrentMonth();
      month.waterRate = newRate;

      // Recalculate all flats in Wing A & B with this rate
      const updateList = (list) => {
        (list || []).forEach(f => {
          f.rate = newRate;
          const gross = Number(f.used || 0) * newRate;
          f.netWater = Math.max(0, gross - Number(f.adv || 0));
          f.needPay = Math.round(f.netWater + Number(f.maint || 0) + Number(f.elec || 0) + Number(f.shaft || 0) + Number(f.oldBal || 0) + Number(f.reqAdv || 0));
        });
      };

      updateList(month.wingA);
      updateList(month.wingB);

      closeModal('modal-water-rate');
      await pushCurrentMonthToCloud();
      refreshAllViews();
      showToast(`Water rate updated to ₹${newRate}/L! Ledger recalculated.`);
    };

    window.recalcEditRow = function() {
      const prev = parseFloat(document.getElementById('edit-flat-prev').value) || 0;
      const curr = parseFloat(document.getElementById('edit-flat-curr').value) || 0;
      const adv = parseFloat(document.getElementById('edit-flat-adv').value) || 0;
      const rate = parseFloat(document.getElementById('edit-flat-rate').value) || 0.15;
      const maint = parseFloat(document.getElementById('edit-flat-maint').value) || 0;
      const elec = parseFloat(document.getElementById('edit-flat-elec').value) || 0;
      const shaft = parseFloat(document.getElementById('edit-flat-shaft').value) || 0;
      const oldBal = parseFloat(document.getElementById('edit-flat-oldbal').value) || 0;

      const used = Math.max(0, curr - prev);
      const grossWater = used * rate;
      const netWater = Math.max(0, grossWater - adv);
      const needPay = Math.round(netWater + maint + elec + shaft + oldBal);

      document.getElementById('edit-flat-needpay').value = needPay;
    };

    window.submitEditFlat = async function(e) {
      e.preventDefault();
      const flatId = document.getElementById('edit-flat-id').value;
      const month = getCurrentMonth();
      let flatObj = (month.wingA || []).find(f => f.id === flatId) || (month.wingB || []).find(f => f.id === flatId);
      if (!flatObj) return;

      flatObj.name = document.getElementById('edit-flat-name').value.trim();
      flatObj.meter = document.getElementById('edit-flat-meter').value.trim();
      flatObj.prev = parseFloat(document.getElementById('edit-flat-prev').value) || 0;
      flatObj.curr = parseFloat(document.getElementById('edit-flat-curr').value) || 0;
      flatObj.adv = parseFloat(document.getElementById('edit-flat-adv').value) || 0;
      flatObj.rate = parseFloat(document.getElementById('edit-flat-rate').value) || 0.15;
      flatObj.maint = parseFloat(document.getElementById('edit-flat-maint').value) || 0;
      flatObj.elec = parseFloat(document.getElementById('edit-flat-elec').value) || 0;
      flatObj.shaft = parseFloat(document.getElementById('edit-flat-shaft').value) || 0;
      flatObj.oldBal = parseFloat(document.getElementById('edit-flat-oldbal').value) || 0;

      flatObj.used = Math.max(0, flatObj.curr - flatObj.prev);
      const gross = flatObj.used * flatObj.rate;
      flatObj.netWater = Math.max(0, gross - flatObj.adv);
      flatObj.needPay = parseFloat(document.getElementById('edit-flat-needpay').value) || 0;
      flatObj.paid = parseFloat(document.getElementById('edit-flat-paid').value) || 0;

      closeModal('modal-edit-flat');
      await pushCurrentMonthToCloud();
      refreshAllViews();
      showToast(`Flat ${flatObj.flat} updated & synchronized real-time!`);
    };

    window.submitSocietyExpense = async function(e) {
      e.preventDefault();
      const title = document.getElementById('expense-title').value.trim();
      const category = document.getElementById('expense-category').value;
      const amount = parseFloat(document.getElementById('expense-amount').value) || 0;
      const date = document.getElementById('expense-date').value;
      const vendor = document.getElementById('expense-vendor').value.trim();
      const fileInput = document.getElementById('expense-voucher-file');

      async function saveExp(voucherUrl) {
        const month = getCurrentMonth();
        if (!month.expenses) month.expenses = [];
        month.expenses.push({
          id: 'exp-' + Date.now(),
          title,
          category,
          amount,
          date,
          vendor,
          voucher: voucherUrl
        });
        closeModal('modal-add-expense');
        await pushCurrentMonthToCloud();
        refreshAllViews();
        showToast(`Society expense of ₹${amount} recorded!`);
      }

      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = async function(evt) {
          await saveExp(evt.target.result);
        };
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        await saveExp('');
      }
    };

    window.submitResidentProof = async function(e) {
      e.preventDefault();
      const flatId = document.getElementById('proof-flat-select').value;
      const amount = parseFloat(document.getElementById('proof-amount').value) || 0;
      const date = document.getElementById('proof-date').value;
      const utr = document.getElementById('proof-utr').value.trim();
      const fileInput = document.getElementById('proof-image-file');

      const month = getCurrentMonth();
      const flatObj = [...(month.wingA || []), ...(month.wingB || [])].find(f => f.id === flatId);

      async function savePrf(imgUrl) {
        if (!month.paymentProofs) month.paymentProofs = [];
        month.paymentProofs.push({
          id: 'proof-' + Date.now(),
          flatId: flatId,
          flat: flatObj ? flatObj.flat : '',
          wing: flatObj ? flatObj.wing : '',
          name: flatObj ? flatObj.name : '',
          amount,
          date,
          utr,
          image: imgUrl,
          status: 'PENDING'
        });
        closeModal('modal-resident-proof');
        await pushCurrentMonthToCloud();
        refreshAllViews();
        showToast("Payment receipt submitted! RWA Committee will verify.");
      }

      if (fileInput.files && fileInput.files[0]) {
        const reader = new FileReader();
        reader.onload = async function(evt) {
          await savePrf(evt.target.result);
        };
        reader.readAsDataURL(fileInput.files[0]);
      } else {
        await savePrf('');
      }
    };

    window.confirmRollover = async function() {
      const newMonthName = document.getElementById('rollover-new-month-name').value.trim();
      if (!newMonthName) {
        showToast("Please enter a valid month title");
        return;
      }

      const curData = getCurrentMonth();
      const newKey = 'cycle-' + Date.now();

      // Wing A Rollover: unpaid balance carries forward as Old Balance; Curr meter becomes Prev meter
      const newWingA = (curData.wingA || []).map(item => {
        const remaining = Math.max(0, item.needPay - (item.paid || 0));
        return {
          ...item,
          prev: item.curr || 0,
          curr: item.curr || 0,
          used: 0,
          netWater: 0,
          oldBal: remaining,
          needPay: remaining + item.maint,
          paid: 0
        };
      });

      // Wing B Rollover: one-time work cleared, unpaid balance carried forward
      const newWingB = (curData.wingB || []).map(item => {
        const remaining = Math.max(0, item.needPay - (item.paid || 0));
        return {
          ...item,
          prev: item.curr || 0,
          curr: item.curr || 0,
          used: 0,
          netWater: 0,
          elec: 0,
          shaft: 0,
          oldBal: remaining,
          needPay: remaining + item.maint,
          paid: 0
        };
      });

      dbState.months[newKey] = {
        name: newMonthName,
        waterRate: curData.waterRate || 0.15,
        wingA: newWingA,
        wingB: newWingB,
        expenses: [],
        paymentProofs: []
      };

      currentMonthKey = newKey;
      closeModal('modal-rollover');
      await pushCurrentMonthToCloud();
      subscribeToMonthCloud(newKey);
      refreshAllViews();
      showToast(`Cycle Rolled Over to ${newMonthName}! Balances Carried Forward.`);
    };

    window.handleAuthAction = function() {
      if (currentRole === 'ADMIN') {
        currentRole = 'VIEWER';
        updateRoleUI();
        showToast("Logged out from Admin Mode.");
      } else {
        openModal('modal-admin-login');
      }
    };

    window.submitAdminLogin = function(e) {
      e.preventDefault();
      const mob = document.getElementById('login-mobile').value.trim();
      const pwd = document.getElementById('login-password').value.trim();
      const errEl = document.getElementById('login-error');

      if (mob === dbState.settings.adminMobile && pwd === dbState.settings.adminPassword) {
        currentRole = 'ADMIN';
        errEl.classList.add('hidden');
        closeModal('modal-admin-login');
        updateRoleUI();
        showToast("Admin authenticated successfully!");
      } else {
        errEl.classList.remove('hidden');
      }
    };

    window.openChangePasswordModal = function() {
      if (currentRole !== 'ADMIN') return;
      document.getElementById('cur-pass-input').value = '';
      document.getElementById('new-pass-input').value = '';
      document.getElementById('change-pass-error').classList.add('hidden');
      openModal('modal-change-password');
    };

    window.submitChangePassword = async function(e) {
      e.preventDefault();
      const cur = document.getElementById('cur-pass-input').value.trim();
      const nw = document.getElementById('new-pass-input').value.trim();
      const err = document.getElementById('change-pass-error');

      if (cur === dbState.settings.adminPassword) {
        dbState.settings.adminPassword = nw;
        await pushSettingsToCloud();
        closeModal('modal-change-password');
        showToast("Admin Password changed & saved to Cloud!");
      } else {
        err.classList.remove('hidden');
      }
    };

    window.handleAdminQrUpload = function(e) {
      if (currentRole !== 'ADMIN') return;
      const file = e.target.files[0];
      if (!file) return;

      const reader = new FileReader();
      reader.onload = async function(evt) {
        dbState.settings.qrImage = evt.target.result;
        await pushSettingsToCloud();
        updateQrDisplay();
        showToast("New Payment QR Code uploaded & synced!");
      };
      reader.readAsDataURL(file);
    };

    function updateQrDisplay() {
      const container = document.getElementById('qr-image-container');
      if (dbState.settings.qrImage) {
        container.innerHTML = `<img src="${dbState.settings.qrImage}" alt="Society QR Code" class="max-h-[220px] object-contain rounded-xl">`;
      } else {
        container.innerHTML = `
          <svg class="w-48 h-48" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="100" height="100" fill="white" rx="8"/>
            <rect x="10" y="10" width="24" height="24" fill="black" rx="4"/>
            <rect x="14" y="14" width="16" height="16" fill="white" rx="2"/>
            <rect x="18" y="18" width="8" height="8" fill="black"/>
            <rect x="66" y="10" width="24" height="24" fill="black" rx="4"/>
            <rect x="70" y="14" width="16" height="16" fill="white" rx="2"/>
            <rect x="74" y="18" width="8" height="8" fill="black"/>
            <rect x="10" y="66" width="24" height="24" fill="black" rx="4"/>
            <rect x="14" y="70" width="16" height="16" fill="white" rx="2"/>
            <rect x="18" y="74" width="8" height="8" fill="black"/>
            <g fill="black">
              <rect x="42" y="12" width="6" height="6"/><rect x="52" y="18" width="6" height="6"/>
              <rect x="42" y="28" width="6" height="6"/><rect x="52" y="34" width="6" height="6"/>
              <rect x="14" y="44" width="6" height="6"/><rect x="26" y="44" width="6" height="6"/>
              <rect x="36" y="44" width="6" height="6"/><rect x="58" y="44" width="6" height="6"/>
              <rect x="70" y="44" width="6" height="6"/><rect x="80" y="44" width="6" height="6"/>
              <rect x="42" y="58" width="6" height="6"/><rect x="52" y="68" width="6" height="6"/>
              <rect x="64" y="60" width="6" height="6"/><rect x="76" y="68" width="6" height="6"/>
            </g>
            <circle cx="50" cy="50" r="11" fill="#f59e0b"/>
            <circle cx="50" cy="50" r="8" fill="#ffffff"/>
            <circle cx="50" cy="50" r="4" fill="#dc2626"/>
            <circle cx="50" cy="50" r="2" fill="#070a14"/>
          </svg>
        `;
      }
      document.getElementById('display-upi-id').textContent = dbState.settings.upiId || '7053600701@upi';
    }

    // Modal Helpers
    window.openModal = function(id) { document.getElementById(id).classList.remove('hidden'); };
    window.closeModal = function(id) { document.getElementById(id).classList.add('hidden'); };
    window.showToast = function(msg) {
      const toast = document.getElementById('toast');
      document.getElementById('toast-message').textContent = msg;
      toast.classList.remove('translate-y-24', 'opacity-0');
      toast.classList.add('translate-y-0', 'opacity-100');
      setTimeout(() => {
        toast.classList.add('translate-y-24', 'opacity-0');
        toast.classList.remove('translate-y-0', 'opacity-100');
      }, 3400);
    };

    window.switchMonth = switchMonth;
    window.setViewTab = function(tab) {
      activeViewTab = tab;
      ['both', 'wing-a', 'wing-b', 'expenses', 'proofs'].forEach(id => {
        const btn = document.getElementById('tab-' + id);
        if ((id === 'both' && tab === 'BOTH') ||
            (id === 'wing-a' && tab === 'WING-A') ||
            (id === 'wing-b' && tab === 'WING-B') ||
            (id === 'expenses' && tab === 'EXPENSES') ||
            (id === 'proofs' && tab === 'PROOFS')) {
          btn.className = "px-4 py-2 rounded-lg text-xs font-bold transition bg-amber-500 text-slate-950 shadow";
        } else {
          btn.className = "px-4 py-2 rounded-lg text-xs font-bold transition text-slate-300 hover:text-white hover:bg-slate-800";
        }
      });

      document.getElementById('section-wing-a').classList.toggle('hidden', !(tab === 'BOTH' || tab === 'WING-A'));
      document.getElementById('section-wing-b').classList.toggle('hidden', !(tab === 'BOTH' || tab === 'WING-B'));
      document.getElementById('section-expenses').classList.toggle('hidden', tab !== 'EXPENSES');
      document.getElementById('section-proofs').classList.toggle('hidden', tab !== 'PROOFS');
    };

    window.handleSearch = function(val) {
      searchQuery = val;
      const month = getCurrentMonth();
      renderWingTable('table-wing-a-body', month.wingA, true);
      renderWingTable('table-wing-b-body', month.wingB, false);
    };

    window.openQrModal = function() {
      updateQrDisplay();
      openModal('modal-qr');
    };

    window.openResidentProofModal = function() {
      document.getElementById('proof-date').value = new Date().toISOString().split('T')[0];
      populateProofSelect();
      openModal('modal-resident-proof');
    };

    window.openAddExpenseModal = function() {
      if (currentRole !== 'ADMIN') {
        showToast("Please login as Admin to add expenses");
        return;
      }
      document.getElementById('expense-date').value = new Date().toISOString().split('T')[0];
      openModal('modal-add-expense');
    };

    window.openRolloverModal = function() {
      if (currentRole !== 'ADMIN') return;
      document.getElementById('rollover-new-month-name').value = "September 2026";
      openModal('modal-rollover');
    };

    function initCanvas() {
      const canvas = document.getElementById('bg-canvas');
      const ctx = canvas.getContext('2d');
      let w, h;
      let stars = [];

      function resize() {
        w = canvas.width = window.innerWidth;
        h = canvas.height = window.innerHeight;
      }
      window.addEventListener('resize', resize);
      resize();

      for (let i = 0; i < 70; i++) {
        stars.push({
          x: Math.random() * w,
          y: Math.random() * h,
          r: Math.random() * 2.2 + 0.5,
          vy: -(Math.random() * 0.35 + 0.15),
          vx: (Math.random() - 0.5) * 0.2,
          alpha: Math.random() * 0.7 + 0.2,
          gold: Math.random() > 0.35
        });
      }

      function draw() {
        ctx.clearRect(0, 0, w, h);
        stars.forEach(s => {
          s.y += s.vy;
          s.x += s.vx;
          if (s.y < 0) { s.y = h + 5; s.x = Math.random() * w; }
          if (s.x < 0 || s.x > w) s.x = Math.random() * w;

          ctx.beginPath();
          ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
          ctx.fillStyle = s.gold 
            ? `rgba(251, 191, 36, ${s.alpha})`
            : `rgba(224, 231, 255, ${s.alpha * 0.8})`;
          ctx.fill();
        });
        requestAnimationFrame(draw);
      }
      draw();
    }

    // Modal background click dismiss
    window.addEventListener('click', (e) => {
      ['modal-admin-login', 'modal-change-password', 'modal-water-rate', 'modal-qr', 'modal-resident-proof', 'modal-edit-flat', 'modal-add-expense', 'modal-rollover', 'modal-image-preview', 'modal-bill-slip'].forEach(id => {
        const modal = document.getElementById(id);
        if (e.target === modal) closeModal(id);
      });
    });

    window.addEventListener('DOMContentLoaded', async () => {
      initCanvas();
      await initCloudSync();
      updateRoleUI();
      refreshAllViews();
    });
  </script>
</body>
</html>
