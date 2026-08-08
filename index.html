<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>V02 — Student Locality & Institutional Geographic Intelligence Dashboard</title>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Chart.js -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  
  <!-- Leaflet CSS & JS -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

  <!-- Google Fonts -->
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
    body {
      font-family: 'Inter', sans-serif;
    }
    .leaflet-popup-content-wrapper {
      border-radius: 0.75rem;
      padding: 0.25rem;
      background: #0f172a;
      color: #f8fafc;
      border: 1px solid #334155;
    }
    .leaflet-popup-tip {
      background: #0f172a;
    }
  </style>
</head>
<body class="bg-slate-900 text-slate-100 min-h-screen flex flex-col font-sans">

  <!-- HEADER BAR -->
  <header class="bg-slate-950 border-b border-slate-800 sticky top-0 z-40 shadow-md">
    <div class="max-w-7xl mx-auto px-4 py-3 sm:px-6 flex flex-col md:flex-row justify-between items-start md:items-center gap-3">
      <div class="flex items-center gap-3">
        <div class="p-2.5 bg-gradient-to-tr from-blue-600 to-indigo-500 rounded-xl shadow-lg shadow-blue-500/20 text-white font-black text-lg">
          KITS
        </div>
        <div>
          <div class="flex items-center gap-2">
            <h1 class="text-base sm:text-lg font-bold text-white tracking-tight">Student Locality & Geographic Dashboard</h1>
            <span class="px-2 py-0.5 text-[10px] uppercase font-bold tracking-wider rounded-full bg-blue-500/10 text-blue-400 border border-blue-500/20">V02 Pro</span>
          </div>
          <p class="text-xs text-slate-400">
            Reference Campus: <span class="text-slate-200 font-medium">Karnataka Institute of Tech & Science (KITS)</span> • Surathkal, Mangaluru, Karnataka
          </p>
        </div>
      </div>

      <div class="flex flex-wrap items-center gap-2 w-full md:w-auto justify-end">
        <div id="storage-status" class="px-3 py-1.5 rounded-lg bg-slate-900 border border-slate-800 text-xs text-emerald-400 flex items-center gap-2">
          <span id="storage-ping" class="h-2 w-2 rounded-full bg-emerald-400 animate-pulse"></span>
          <span id="storage-status-text">Local Storage Active</span>
        </div>

        <!-- USER AUTHENTICATION BADGE & LOGIN TRIGGER -->
        <div id="user-auth-badge" class="px-3 py-1.5 rounded-lg bg-slate-900 border border-slate-800 text-xs text-slate-200 flex items-center gap-2">
          <span class="w-2 h-2 rounded-full bg-blue-400"></span>
          <span id="user-display-name" class="font-medium">Administrator</span>
          <span id="user-role-badge" class="px-1.5 py-0.5 text-[9px] rounded uppercase font-extrabold bg-blue-500/20 text-blue-400 border border-blue-500/30">ADMIN</span>
        </div>
        <button id="btn-open-login" class="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-slate-200 text-xs font-semibold rounded-lg border border-slate-700 transition flex items-center gap-1.5">
          <span>👤</span> <span id="login-btn-text">Switch Account</span>
        </button>

        <button id="btn-sync-settings" class="px-3 py-1.5 bg-indigo-600 hover:bg-indigo-500 text-white text-xs font-semibold rounded-lg transition flex items-center gap-1.5 shadow-sm">
          <span>📲</span> Sync Devices
        </button>
        <button id="btn-export" class="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-slate-200 text-xs font-semibold rounded-lg border border-slate-700 transition flex items-center gap-1.5">
          <span>📥</span> Export JSON
        </button>
        <button id="btn-import-trigger" class="px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-slate-200 text-xs font-semibold rounded-lg border border-slate-700 transition flex items-center gap-1.5">
          <span>📤</span> Import
        </button>
        <input type="file" id="import-file" accept=".json" class="hidden">
        <button id="btn-prompt-reset" class="px-3 py-1.5 bg-rose-900/40 hover:bg-rose-800/60 text-rose-300 border border-rose-700/50 text-xs font-semibold rounded-lg transition flex items-center gap-1.5">
          <span>↺</span> Reset Demo
        </button>
      </div>
    </div>

    <!-- TABS NAVIGATION -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 border-t border-slate-800/80 flex space-x-1 sm:space-x-4 overflow-x-auto">
      <button data-tab="tab-overview" class="nav-tab px-4 py-2.5 text-xs sm:text-sm font-semibold border-b-2 border-blue-500 text-blue-400 flex items-center gap-2 whitespace-nowrap transition">
        <span>📊</span> Overview & Analytics
      </button>
      <button data-tab="tab-map" class="nav-tab px-4 py-2.5 text-xs sm:text-sm font-semibold border-b-2 border-transparent text-slate-400 hover:text-slate-200 flex items-center gap-2 whitespace-nowrap transition">
        <span>🗺️</span> Geographic Spatial Map
      </button>
      <button data-tab="tab-students" class="nav-tab px-4 py-2.5 text-xs sm:text-sm font-semibold border-b-2 border-transparent text-slate-400 hover:text-slate-200 flex items-center gap-2 whitespace-nowrap transition">
        <span>📋</span> Student Registry
      </button>
      <button data-tab="tab-naac" class="nav-tab px-4 py-2.5 text-xs sm:text-sm font-semibold border-b-2 border-transparent text-slate-400 hover:text-slate-200 flex items-center gap-2 whitespace-nowrap transition">
        <span>📑</span> NAAC & NIRF Reports
      </button>
    </div>
  </header>

  <!-- MAIN CONTAINER -->
  <div class="max-w-7xl mx-auto px-4 py-6 sm:px-6 flex-grow w-full space-y-6">

    <!-- TAB 1: OVERVIEW & ANALYTICS -->
    <section id="tab-overview" class="tab-content space-y-6">
      
      <!-- TOP METRIC CARDS -->
      <div>
        <div class="flex justify-between items-center mb-3">
          <h2 class="text-xs font-bold uppercase tracking-wider text-slate-400">Accreditation Geographic Distribution (NAAC / NIRF)</h2>
          <span id="total-student-badge" class="text-xs bg-slate-800 text-slate-300 px-2.5 py-1 rounded-full font-semibold border border-slate-700">Total Students: 0</span>
        </div>

        <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-3 sm:gap-4">
          
          <div class="bg-slate-800/80 backdrop-blur border border-emerald-500/20 p-4 rounded-xl shadow-sm text-center relative overflow-hidden group">
            <div class="absolute top-0 left-0 w-1 h-full bg-emerald-500"></div>
            <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide">Local (Surathkal)</span>
            <div id="count-local" class="text-2xl sm:text-3xl font-extrabold text-emerald-400 my-1">0</div>
            <span id="pct-local" class="text-xs text-emerald-300 font-medium bg-emerald-500/10 px-2 py-0.5 rounded-full inline-block">0%</span>
          </div>

          <div class="bg-slate-800/80 backdrop-blur border border-sky-500/20 p-4 rounded-xl shadow-sm text-center relative overflow-hidden group">
            <div class="absolute top-0 left-0 w-1 h-full bg-sky-500"></div>
            <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide">District (Dakshina Kannada)</span>
            <div id="count-district" class="text-2xl sm:text-3xl font-extrabold text-sky-400 my-1">0</div>
            <span id="pct-district" class="text-xs text-sky-300 font-medium bg-sky-500/10 px-2 py-0.5 rounded-full inline-block">0%</span>
          </div>

          <div class="bg-slate-800/80 backdrop-blur border border-amber-500/20 p-4 rounded-xl shadow-sm text-center relative overflow-hidden group">
            <div class="absolute top-0 left-0 w-1 h-full bg-amber-500"></div>
            <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide">Within State (Karnataka)</span>
            <div id="count-state" class="text-2xl sm:text-3xl font-extrabold text-amber-400 my-1">0</div>
            <span id="pct-state" class="text-xs text-amber-300 font-medium bg-amber-500/10 px-2 py-0.5 rounded-full inline-block">0%</span>
          </div>

          <div class="bg-slate-800/80 backdrop-blur border border-orange-500/20 p-4 rounded-xl shadow-sm text-center relative overflow-hidden group">
            <div class="absolute top-0 left-0 w-1 h-full bg-orange-500"></div>
            <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide">Other States (India)</span>
            <div id="count-otherstate" class="text-2xl sm:text-3xl font-extrabold text-orange-400 my-1">0</div>
            <span id="pct-otherstate" class="text-xs text-orange-300 font-medium bg-orange-500/10 px-2 py-0.5 rounded-full inline-block">0%</span>
          </div>

          <div class="bg-slate-800/80 backdrop-blur border border-pink-500/20 p-4 rounded-xl shadow-sm text-center relative overflow-hidden col-span-2 sm:col-span-1 group">
            <div class="absolute top-0 left-0 w-1 h-full bg-pink-500"></div>
            <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide">International</span>
            <div id="count-intl" class="text-2xl sm:text-3xl font-extrabold text-pink-400 my-1">0</div>
            <span id="pct-intl" class="text-xs text-pink-300 font-medium bg-pink-500/10 px-2 py-0.5 rounded-full inline-block">0%</span>
          </div>

        </div>
      </div>

      <!-- CHARTS GRID -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
        
        <!-- Donut Breakdown Chart -->
        <div class="lg:col-span-5 bg-slate-800/60 border border-slate-700/60 p-5 rounded-2xl flex flex-col justify-between">
          <div class="flex justify-between items-center mb-2">
            <h3 class="text-sm font-bold text-slate-200 flex items-center gap-2">
              <span>🍩</span> Locality Category Ratio
            </h3>
            <span class="text-[10px] text-slate-400 bg-slate-900/80 px-2 py-1 rounded">NAAC Criteria 2.1</span>
          </div>
          <div class="relative w-full h-64 flex items-center justify-center p-2">
            <canvas id="chart-locality-donut"></canvas>
          </div>
          <p class="text-xs text-slate-400 text-center mt-2 italic">
            Automated tier ranking relative to reference campus at Surathkal, Karnataka.
          </p>
        </div>

        <!-- Bar Chart: Top Representation States -->
        <div class="lg:col-span-7 bg-slate-800/60 border border-slate-700/60 p-5 rounded-2xl flex flex-col justify-between">
          <div class="flex justify-between items-center mb-2">
            <h3 class="text-sm font-bold text-slate-200 flex items-center gap-2">
              <span>🏛️</span> Top Regional & State Representation
            </h3>
            <span class="text-[10px] text-slate-400 bg-slate-900/80 px-2 py-1 rounded">Diversity Metrics</span>
          </div>
          <div class="relative w-full h-64 p-2">
            <canvas id="chart-states-bar"></canvas>
          </div>
          <div class="flex justify-between items-center text-xs text-slate-400 mt-2">
            <span>Outer State Student Share: <strong id="stat-out-state-pct" class="text-orange-400">0%</strong></span>
            <span>International Diversity: <strong id="stat-intl-pct" class="text-pink-400">0%</strong></span>
          </div>
        </div>

      </div>

      <!-- DISTANCE RADIUS STATS -->
      <div class="bg-gradient-to-r from-slate-800 to-slate-900 border border-slate-700/80 rounded-2xl p-5 shadow-lg">
        <h3 class="text-sm font-bold text-slate-200 mb-3 flex items-center gap-2">
          <span>📐</span> Spatial Commute & Distance Band Radius (From Surathkal Campus)
        </h3>
        <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 text-center">
          <div class="p-3 bg-slate-900/60 rounded-xl border border-slate-800">
            <span class="text-xs text-slate-400">Within 25 km</span>
            <div id="radius-25" class="text-xl font-bold text-blue-400 mt-1">0</div>
            <span class="text-[10px] text-slate-500">Day Scholars / Local</span>
          </div>
          <div class="p-3 bg-slate-900/60 rounded-xl border border-slate-800">
            <span class="text-xs text-slate-400">25 - 150 km</span>
            <div id="radius-150" class="text-xl font-bold text-indigo-400 mt-1">0</div>
            <span class="text-[10px] text-slate-500">Coastal / Neighboring</span>
          </div>
          <div class="p-3 bg-slate-900/60 rounded-xl border border-slate-800">
            <span class="text-xs text-slate-400">150 - 800 km</span>
            <div id="radius-800" class="text-xl font-bold text-purple-400 mt-1">0</div>
            <span class="text-[10px] text-slate-500">Inter-District / State</span>
          </div>
          <div class="p-3 bg-slate-900/60 rounded-xl border border-slate-800">
            <span class="text-xs text-slate-400">&gt; 800 km & Global</span>
            <div id="radius-far" class="text-xl font-bold text-pink-400 mt-1">0</div>
            <span class="text-[10px] text-slate-500">National / International</span>
          </div>
        </div>
      </div>

    </section>

    <!-- TAB 2: GEOGRAPHIC SPATIAL MAP -->
    <section id="tab-map" class="tab-content hidden space-y-4">
      <div class="bg-slate-800/80 border border-slate-700 p-4 rounded-2xl flex flex-col md:flex-row justify-between items-start md:items-center gap-3">
        <div>
          <h2 class="text-base font-bold text-white flex items-center gap-2">
            <span>🗺️</span> Spatial Distribution Map
          </h2>
          <p class="text-xs text-slate-400">
            Interactive GIS plotting of student home locations relative to KITS Campus (Surathkal, Mangaluru: 13.0108° N, 74.7943° E).
          </p>
        </div>
        <div class="flex flex-wrap items-center gap-3 text-xs">
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded-full bg-emerald-500"></span> Local</span>
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded-full bg-sky-500"></span> District</span>
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded-full bg-amber-500"></span> Within State</span>
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded-full bg-orange-500"></span> Other State</span>
          <span class="flex items-center gap-1"><span class="w-3 h-3 rounded-full bg-pink-500"></span> Intl</span>
        </div>
      </div>

      <div class="relative w-full h-[540px] rounded-2xl overflow-hidden border border-slate-700 shadow-xl bg-slate-950">
        <div id="leaflet-map-container" class="w-full h-full"></div>
      </div>
    </section>

    <!-- TAB 3: STUDENT REGISTRY & FORM -->
    <section id="tab-students" class="tab-content hidden grid grid-cols-1 lg:grid-cols-12 gap-6">
      
      <!-- LEFT FORM PANEL -->
      <div class="lg:col-span-4 bg-slate-800/80 border border-slate-700 p-5 rounded-2xl h-fit space-y-4">
        <div class="flex justify-between items-center border-b border-slate-700 pb-3">
          <h3 id="form-title" class="text-sm font-bold text-white">Add New Student Record</h3>
          <span id="form-mode-badge" class="text-[10px] bg-blue-500/20 text-blue-300 border border-blue-500/30 px-2 py-0.5 rounded font-mono">NEW</span>
        </div>
        
        <form id="student-form" class="space-y-3 text-xs">
          <input type="hidden" id="edit-id" value="">
          
          <div>
            <label class="block font-semibold text-slate-300 mb-1" for="name">Full Name *</label>
            <input type="text" id="name" required placeholder="e.g. Aarav Sharma" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
          </div>

          <div>
            <label class="block font-semibold text-slate-300 mb-1" for="program">Academic Program *</label>
            <input type="text" id="program" required value="B.Tech CSE" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
          </div>

          <div class="grid grid-cols-2 gap-2">
            <div>
              <label class="block font-semibold text-slate-300 mb-1" for="city">City / Town *</label>
              <input type="text" id="city" required placeholder="Surathkal" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
            </div>
            <div>
              <label class="block font-semibold text-slate-300 mb-1" for="district">District *</label>
              <input type="text" id="district" required placeholder="Dakshina Kannada" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
            </div>
          </div>

          <div class="grid grid-cols-2 gap-2">
            <div>
              <label class="block font-semibold text-slate-300 mb-1" for="state">State / Province *</label>
              <input type="text" id="state" required placeholder="Karnataka" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
            </div>
            <div>
              <label class="block font-semibold text-slate-300 mb-1" for="country">Country *</label>
              <input type="text" id="country" required value="India" class="w-full px-3 py-2 rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
            </div>
          </div>

          <div class="pt-2 flex flex-col gap-2">
            <button type="submit" id="form-submit-btn" class="w-full py-2.5 bg-blue-600 hover:bg-blue-500 text-white font-semibold rounded-lg shadow-sm transition">
              Create & Auto-Classify Location
            </button>
            <button type="button" id="form-cancel-btn" class="hidden w-full py-2 bg-slate-700 hover:bg-slate-600 text-slate-200 font-semibold rounded-lg transition">
              Cancel Edit
            </button>
          </div>
        </form>

        <!-- BATCH GENERATOR -->
        <div class="border-t border-slate-700/80 pt-4 mt-4 space-y-2">
          <span class="text-[11px] font-bold text-slate-400 uppercase tracking-wide block">⚡ Quick Sample Generator</span>
          <div class="grid grid-cols-2 gap-2">
            <button id="btn-gen-10" class="py-1.5 px-2 bg-slate-900 hover:bg-slate-950 border border-slate-700 text-slate-300 rounded text-[11px] transition">
              +10 Sample Students
            </button>
            <button id="btn-gen-25" class="py-1.5 px-2 bg-slate-900 hover:bg-slate-950 border border-slate-700 text-slate-300 rounded text-[11px] transition">
              +25 Random Batch
            </button>
          </div>
        </div>
      </div>

      <!-- RIGHT DATA TABLE PANEL -->
      <div class="lg:col-span-8 bg-slate-800/80 border border-slate-700 p-5 rounded-2xl space-y-4">
        
        <div class="flex flex-col sm:flex-row justify-between items-stretch sm:items-center gap-3">
          <div class="relative flex-1">
            <input type="text" id="search-input" placeholder="Search student name, ID, city, or district..." class="w-full pl-9 pr-3 py-2 text-xs rounded-lg bg-slate-900 border border-slate-700 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
            <svg class="w-4 h-4 absolute left-3 top-2.5 text-slate-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
          </div>

          <select id="filter-category" class="px-3 py-2 text-xs rounded-lg bg-slate-900 border border-slate-700 text-slate-200 focus:ring-2 focus:ring-blue-500 outline-none">
            <option value="All">All Locality Categories</option>
            <option value="Local">Local (Surathkal)</option>
            <option value="District">District (Dakshina Kannada)</option>
            <option value="Within State">Within State (Karnataka)</option>
            <option value="Other State">Other State (India)</option>
            <option value="International">International</option>
          </select>
        </div>

        <div class="overflow-x-auto rounded-xl border border-slate-700">
          <table class="w-full text-left text-xs">
            <thead class="bg-slate-900/90 text-slate-400 font-semibold border-b border-slate-700">
              <tr>
                <th class="p-3">Student & ID</th>
                <th class="p-3">Origin Address</th>
                <th class="p-3">Est. Distance</th>
                <th class="p-3">Locality Classification</th>
                <th class="p-3 text-right">Actions</th>
              </tr>
            </thead>
            <tbody id="student-table-body" class="divide-y divide-slate-700/60 text-slate-200">
              <!-- Dynamic Rows -->
            </tbody>
          </table>
        </div>

      </div>

    </section>

    <!-- TAB 4: NAAC & NIRF ACCREDITATION REPORTS -->
    <section id="tab-naac" class="tab-content hidden space-y-6">
      <div class="bg-slate-800/80 border border-slate-700 p-5 rounded-2xl flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
        <div>
          <h2 class="text-base font-bold text-white flex items-center gap-2">
            <span>📑</span> NAAC Criterion 2.1 & NIRF Geographic Diversity Report
          </h2>
          <p class="text-xs text-slate-400">
            Export compliant geographic data matrices formatted for institutional SSR submission and NIRF Ranking data sheets.
          </p>
        </div>
        <button id="btn-copy-report" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white text-xs font-semibold rounded-lg shadow-md transition flex items-center gap-2">
          <span>📋</span> Copy Formatted Table
        </button>
      </div>

      <div class="bg-slate-800/80 border border-slate-700 rounded-2xl overflow-hidden p-5">
        <h3 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-4">Institutional Geographic Breakdown Table</h3>
        
        <div class="overflow-x-auto">
          <table id="naac-report-table" class="w-full text-left text-xs border-collapse">
            <thead>
              <tr class="bg-slate-900 border-b border-slate-700 text-slate-300 font-bold">
                <th class="p-3 border-r border-slate-800">Category Tier</th>
                <th class="p-3 border-r border-slate-800">Criteria Scope</th>
                <th class="p-3 border-r border-slate-800 text-center">Student Count</th>
                <th class="p-3 border-r border-slate-800 text-center">Percentage (%)</th>
                <th class="p-3 text-slate-400">NAAC / NIRF Metric Mapping</th>
              </tr>
            </thead>
            <tbody id="naac-table-body" class="divide-y divide-slate-700/60 text-slate-200 font-mono">
              <!-- Dynamic Report Rows -->
            </tbody>
          </table>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div class="bg-slate-800/60 border border-slate-700 p-5 rounded-2xl space-y-2">
          <h4 class="text-xs font-bold text-blue-400 uppercase tracking-wide">NAAC Metric 2.1.1 & 2.1.2 Guidelines</h4>
          <p class="text-xs text-slate-300 leading-relaxed">
            NAAC assesses the institutional capability to attract students from outside the home state and country to evaluate diversity. A healthy balance of <strong>Within State</strong> vs. <strong>Other States / International</strong> earns optimal metric points.
          </p>
        </div>
        <div class="bg-slate-800/60 border border-slate-700 p-5 rounded-2xl space-y-2">
          <h4 class="text-xs font-bold text-emerald-400 uppercase tracking-wide">NIRF Student Diversity Metric</h4>
          <p class="text-xs text-slate-300 leading-relaxed">
            NIRF calculates "Out of State" percentage ($P_{OS}$) and "Out of Country" percentage ($P_{OC}$) to award score points under the <em>Outreach and Inclusivity (OI)</em> parameter.
          </p>
        </div>
      </div>
    </section>

  </div>

  <!-- TOAST CONTAINER -->
  <div id="toast-container" class="fixed bottom-5 right-5 z-50 flex flex-col gap-2 pointer-events-none"></div>

  <!-- CROSS-DEVICE SYNC MODAL -->
  <div id="sync-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 rounded-2xl p-6 max-w-md w-full shadow-2xl border border-slate-800 space-y-4">
      <div class="flex justify-between items-center border-b border-slate-800 pb-3">
        <h3 class="text-sm font-bold text-white flex items-center gap-2">
          <span>📲</span> Connect Phone & Laptop Live
        </h3>
        <button id="btn-sync-close" class="text-slate-400 hover:text-slate-200 font-bold text-lg">&times;</button>
      </div>

      <p class="text-xs text-slate-400 leading-relaxed">
        To sync student records in real time between your phone and laptop, paste your database configuration below.
      </p>

      <div>
        <label class="block text-xs font-semibold text-slate-300 mb-1">Database Config (JSON)</label>
        <textarea id="sync-config-input" rows="5" placeholder='{
  "apiKey": "...",
  "authDomain": "...",
  "projectId": "...",
  "storageBucket": "...",
  "messagingSenderId": "...",
  "appId": "..."
}' class="w-full p-2.5 text-xs font-mono bg-slate-950 text-slate-200 rounded-lg border border-slate-700 focus:ring-2 focus:ring-blue-500 outline-none"></textarea>
      </div>

      <div class="flex items-center justify-between pt-2">
        <button id="btn-clear-sync" class="px-3 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs font-semibold rounded-lg transition">
          Reset Default
        </button>
        <div class="flex gap-2">
          <button id="btn-sync-modal-cancel" class="px-4 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs font-semibold rounded-lg transition">Cancel</button>
          <button id="btn-save-sync" class="px-4 py-2 bg-blue-600 hover:bg-blue-500 text-white text-xs font-semibold rounded-lg transition">Save & Link</button>
        </div>
      </div>
    </div>
  </div>

  <!-- RESET CONFIRMATION MODAL -->
  <div id="reset-modal" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="bg-slate-900 rounded-2xl p-6 max-w-sm w-full shadow-2xl border border-slate-800 space-y-4">
      <h3 class="text-base font-bold text-white">Reset Demo Data?</h3>
      <p class="text-xs text-slate-400 leading-relaxed">This will revert student records back to the default 30 sample students across all connected devices.</p>
      <div class="flex gap-2 justify-end pt-2">
        <button id="btn-modal-cancel" class="px-4 py-2 bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs font-semibold rounded-lg transition">Cancel</button>
        <button id="btn-modal-confirm" class="px-4 py-2 bg-rose-600 hover:bg-rose-500 text-white text-xs font-semibold rounded-lg transition">Reset Data</button>
      </div>
    </div>
  </div>

  <!-- LOGIN & AUTHENTICATION MODAL -->
  <div id="login-modal" class="fixed inset-0 bg-slate-950/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">
    <div class="bg-slate-900 rounded-2xl p-6 sm:p-8 max-w-md w-full shadow-2xl border border-slate-800 space-y-6 relative overflow-hidden">
      <!-- Top Decorative Gradient Line -->
      <div class="absolute top-0 left-0 right-0 h-1.5 bg-gradient-to-r from-blue-600 via-indigo-500 to-emerald-400"></div>
      
      <div class="flex justify-between items-start">
        <div class="flex items-center gap-3">
          <div class="p-2.5 bg-gradient-to-tr from-blue-600 to-indigo-500 rounded-xl shadow-lg text-white font-black text-lg">
            KITS
          </div>
          <div>
            <h3 class="text-lg font-bold text-white tracking-tight">Institutional Portal Login</h3>
            <p class="text-xs text-slate-400">Role-Based Access Control</p>
          </div>
        </div>
        <button id="btn-login-close" class="text-slate-400 hover:text-slate-200 font-bold text-xl leading-none">&times;</button>
      </div>

      <!-- SECTION 1: ADMINISTRATORS (4 ADMINS) -->
      <div>
        <label class="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">Section 1: Administrators (Full Privileges - Password Req.)</label>
        <div class="grid grid-cols-2 sm:grid-cols-4 gap-2">
          <button type="button" data-role="admin" data-admin="Thejes" class="admin-preset-btn p-2 rounded-xl border border-blue-500 bg-blue-500/10 text-blue-400 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">👑</span>
            <span class="text-[11px] font-bold">Thejes</span>
            <span class="text-[9px] text-slate-400">Admin</span>
          </button>
          <button type="button" data-role="admin" data-admin="Melbin" class="admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">👑</span>
            <span class="text-[11px] font-bold">Melbin</span>
            <span class="text-[9px] text-slate-400">Admin</span>
          </button>
          <button type="button" data-role="admin" data-admin="Nithin" class="admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">👑</span>
            <span class="text-[11px] font-bold">Nithin</span>
            <span class="text-[9px] text-slate-400">Admin</span>
          </button>
          <button type="button" data-role="admin" data-admin="Shashidhara" class="admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">👑</span>
            <span class="text-[11px] font-bold">Shashidhara</span>
            <span class="text-[9px] text-slate-400">Admin</span>
          </button>
        </div>
      </div>

      <!-- SECTION 2: STUDENT & FACULTY (VIEWERS) -->
      <div>
        <label class="block text-xs font-semibold text-slate-400 uppercase tracking-wider mb-2">Section 2: Student & Faculty (Quick Viewer Sign-In)</label>
        <div class="grid grid-cols-2 gap-2">
          <button type="button" data-role="student" data-admin="Aarav Shetty" class="admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">🎒</span>
            <span class="text-[11px] font-bold">Student Rep</span>
            <span class="text-[9px] text-slate-400">Viewer Mode</span>
          </button>
          <button type="button" data-role="student" data-admin="Dr. Ramesh Rao" class="admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1">
            <span class="text-sm">👨‍🏫</span>
            <span class="text-[11px] font-bold">Faculty Member</span>
            <span class="text-[9px] text-slate-400">Viewer Mode</span>
          </button>
        </div>
      </div>

      <!-- LOGIN FORM -->
      <form id="login-form" class="space-y-4 text-xs">
        <input type="hidden" id="login-selected-admin" value="Thejes">
        <input type="hidden" id="login-selected-role" value="admin">

        <div id="name-input-container" class="hidden">
          <label class="block font-semibold text-slate-300 mb-1" id="name-input-label" for="login-custom-name">Enter Student Name</label>
          <input type="text" id="login-custom-name" placeholder="" class="w-full px-3 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
        </div>

        <div id="password-field-container">
          <label class="block font-semibold text-slate-300 mb-1" for="login-password">Security Password</label>
          <input type="password" id="login-password" placeholder="Enter administrator password" class="w-full px-3 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-slate-100 focus:ring-2 focus:ring-blue-500 outline-none">
        </div>

        <button type="submit" class="w-full py-3 bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-500 hover:to-indigo-500 text-white font-bold rounded-xl shadow-lg shadow-blue-500/20 transition flex items-center justify-center gap-2 text-xs">
          <span>🔓</span> Switch Account & Sign In
        </button>
      </form>

      <div class="border-t border-slate-800/80 pt-3 text-center text-[11px] text-slate-500">
        Karnataka Institute of Technology & Science • Role-Based Portal
      </div>
    </div>
  </div>

  <!-- APPLICATION CORE LOGIC SCRIPT -->
  <script>
    // --- REFERENCE CAMPUS COORDINATES ---
    const CAMPUS = {
      name: "Karnataka Institute of Tech & Science (KITS)",
      city: "Surathkal",
      district: "Dakshina Kannada",
      state: "Karnataka",
      country: "India",
      lat: 13.0108,
      lng: 74.7943
    };

    // --- SEED / INITIAL STUDENTS ---
    const INITIAL_STUDENTS = [
      { id: "KITS-2026-001", name: "Aarav Shetty", program: "B.Tech CSE", city: "Surathkal", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 13.0125, lng: 74.7920 },
      { id: "KITS-2026-002", name: "Ananya Rao", program: "B.Tech ECE", city: "Mangaluru", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 12.9141, lng: 74.8560 },
      { id: "KITS-2026-003", name: "Mohammed Zayd", program: "B.Tech AI & DS", city: "Udupi", district: "Udupi", state: "Karnataka", country: "India", lat: 13.3409, lng: 74.7421 },
      { id: "KITS-2026-004", name: "Sneha Kamath", program: "B.Tech Mechanical", city: "Kundapura", district: "Udupi", state: "Karnataka", country: "India", lat: 13.6288, lng: 74.6932 },
      { id: "KITS-2026-005", name: "Rohan D'Souza", program: "B.Tech Civil", city: "Mulki", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 13.0905, lng: 74.7981 },
      { id: "KITS-2026-006", name: "Pooja Hegde", program: "B.Tech CSE", city: "Bengaluru", district: "Bengaluru Urban", state: "Karnataka", country: "India", lat: 12.9716, lng: 77.5946 },
      { id: "KITS-2026-007", name: "Kiran Kumar", program: "B.Tech EEE", city: "Mysuru", district: "Mysuru", state: "Karnataka", country: "India", lat: 12.2958, lng: 76.6394 },
      { id: "KITS-2026-008", name: "Divya Nambiar", program: "B.Tech CSE", city: "Kochi", district: "Ernakulam", state: "Kerala", country: "India", lat: 9.9312, lng: 76.2673 },
      { id: "KITS-2026-009", name: "Aditya Menon", program: "B.Tech AI & DS", city: "Thiruvananthapuram", district: "Thiruvananthapuram", state: "Kerala", country: "India", lat: 8.5241, lng: 76.9366 },
      { id: "KITS-2026-010", name: "Tanvi Sharma", program: "B.Tech CSE", city: "Mumbai", district: "Mumbai Suburban", state: "Maharashtra", country: "India", lat: 19.0760, lng: 72.8777 },
      { id: "KITS-2026-011", name: "Rahul Verma", program: "B.Tech ECE", city: "Pune", district: "Pune", state: "Maharashtra", country: "India", lat: 18.5204, lng: 73.8567 },
      { id: "KITS-2026-012", name: "Akash Patel", program: "B.Tech Mechanical", city: "Ahmedabad", district: "Ahmedabad", state: "Gujarat", country: "India", lat: 23.0225, lng: 72.5714 },
      { id: "KITS-2026-013", name: "Neha Gupta", program: "B.Tech CSE", city: "New Delhi", district: "New Delhi", state: "Delhi", country: "India", lat: 28.6139, lng: 77.2090 },
      { id: "KITS-2026-014", name: "Abhishek Roy", program: "B.Tech AI & DS", city: "Kolkata", district: "Kolkata", state: "West Bengal", country: "India", lat: 22.5726, lng: 88.3639 },
      { id: "KITS-2026-015", name: "Siddharth Reddy", program: "B.Tech CSE", city: "Hyderabad", district: "Hyderabad", state: "Telangana", country: "India", lat: 17.3850, lng: 78.4867 },
      { id: "KITS-2026-016", name: "Sai Kumar", program: "B.Tech EEE", city: "Chennai", district: "Chennai", state: "Tamil Nadu", country: "India", lat: 13.0827, lng: 80.2707 },
      { id: "KITS-2026-017", name: "Meera Nair", program: "B.Tech Civil", city: "Coimbatore", district: "Coimbatore", state: "Tamil Nadu", country: "India", lat: 11.0168, lng: 76.9558 },
      { id: "KITS-2026-018", name: "Tenzin Norbu", program: "B.Tech CSE", city: "Gangtok", district: "East Sikkim", state: "Sikkim", country: "India", lat: 27.3389, lng: 88.6065 },
      { id: "KITS-2026-019", name: "Rina Chakma", program: "B.Tech ECE", city: "Guwahati", district: "Kamrup Metropolitan", state: "Assam", country: "India", lat: 26.1445, lng: 91.7362 },
      { id: "KITS-2026-020", name: "Liam Smith", program: "B.Tech CSE", city: "London", district: "Greater London", state: "England", country: "United Kingdom", lat: 51.5074, lng: -0.1278 },
      { id: "KITS-2026-021", name: "Aisha Al-Mansoor", program: "B.Tech AI & DS", city: "Dubai", district: "Dubai", state: "Dubai", country: "United Arab Emirates", lat: 25.2048, lng: 55.2708 },
      { id: "KITS-2026-022", name: "Harshith Rao", program: "B.Tech CSE", city: "Mangaluru", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 12.9250, lng: 74.8400 },
      { id: "KITS-2026-023", name: "Shreya Pai", program: "B.Tech ECE", city: "Surathkal", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 13.0090, lng: 74.7980 },
      { id: "KITS-2026-024", name: "Varun Suvarna", program: "B.Tech Mechanical", city: "Surathkal", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 13.0150, lng: 74.7900 },
      { id: "KITS-2026-025", name: "Nischitha Bhat", program: "B.Tech CSE", city: "Bantwal", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 12.8756, lng: 75.0384 },
      { id: "KITS-2026-026", name: "Pradeep Nayak", program: "B.Tech Civil", city: "Puttur", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 12.7623, lng: 75.2013 },
      { id: "KITS-2026-027", name: "Sumanth M.", program: "B.Tech EEE", city: "Hubballi", district: "Dharwad", state: "Karnataka", country: "India", lat: 15.3647, lng: 75.1240 },
      { id: "KITS-2026-028", name: "Kavya S.", program: "B.Tech CSE", city: "Belagavi", district: "Belagavi", state: "Karnataka", country: "India", lat: 15.8497, lng: 74.4977 },
      { id: "KITS-2026-029", name: "Vikramaditya", program: "B.Tech AI & DS", city: "Jaipur", district: "Jaipur", state: "Rajasthan", country: "India", lat: 26.9124, lng: 75.7873 },
      { id: "KITS-2026-030", name: "Kenji Sato", program: "B.Tech CSE", city: "Tokyo", district: "Tokyo Metropolis", state: "Tokyo", country: "Japan", lat: 35.6762, lng: 139.6503 }
    ];

    // --- APPLICATION STATE ---
    let students = [];
    let currentUser = {
      name: "Thejes",
      email: "thejes@kits.edu.in",
      role: "admin"
    };
    let leafletMap = null;
    let markersLayer = null;
    let donutChartInstance = null;
    let barChartInstance = null;

    // --- UTILITIES: DISTANCE & CLASSIFICATION ---
    function calculateDistance(lat1, lon1, lat2, lon2) {
      const R = 6371; // Earth radius in km
      const dLat = (lat2 - lat1) * Math.PI / 180;
      const dLon = (lon2 - lon1) * Math.PI / 180;
      const a = Math.sin(dLat/2) * Math.sin(dLat/2) +
                Math.cos(lat1 * Math.PI / 180) * Math.cos(lat2 * Math.PI / 180) *
                Math.sin(dLon/2) * Math.sin(dLon/2);
      const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));
      return R * c;
    }

    function classifyLocality(student) {
      if (student.country && student.country.toLowerCase() !== 'india') {
        return 'International';
      }
      if (student.state && student.state.toLowerCase() !== 'karnataka') {
        return 'Other State';
      }
      if (student.city && student.city.toLowerCase() === 'surathkal') {
        return 'Local';
      }
      if (student.district && student.district.toLowerCase() === 'dakshina kannada') {
        return 'District';
      }
      return 'Within State';
    }

    function getBadgeClass(category) {
      switch(category) {
        case 'Local': return 'bg-emerald-500/10 text-emerald-400 border-emerald-500/30';
        case 'District': return 'bg-sky-500/10 text-sky-400 border-sky-500/30';
        case 'Within State': return 'bg-amber-500/10 text-amber-400 border-amber-500/30';
        case 'Other State': return 'bg-orange-500/10 text-orange-400 border-orange-500/30';
        case 'International': return 'bg-pink-500/10 text-pink-400 border-pink-500/30';
        default: return 'bg-slate-700 text-slate-300 border-slate-600';
      }
    }

    function getMarkerColor(category) {
      switch(category) {
        case 'Local': return '#10b981';
        case 'District': return '#0ea5e9';
        case 'Within State': return '#f59e0b';
        case 'Other State': return '#f97316';
        case 'International': return '#ec4899';
        default: return '#64748b';
      }
    }

    function showToast(message, type = 'success') {
      const container = document.getElementById('toast-container');
      const toast = document.createElement('div');
      const bg = type === 'success' ? 'bg-emerald-600 text-white' : type === 'error' ? 'bg-rose-600 text-white' : 'bg-slate-800 text-slate-100 border border-slate-700';
      toast.className = `${bg} px-4 py-2.5 rounded-xl text-xs font-semibold shadow-xl transition transform translate-y-2 opacity-0 flex items-center gap-2`;
      toast.innerHTML = `<span>${type === 'success' ? '✅' : type === 'error' ? '⚠️' : 'ℹ️'}</span> ${message}`;
      container.appendChild(toast);
      
      setTimeout(() => {
        toast.classList.remove('translate-y-2', 'opacity-0');
      }, 10);

      setTimeout(() => {
        toast.classList.add('translate-y-2', 'opacity-0');
        setTimeout(() => toast.remove(), 300);
      }, 3500);
    }

    // --- PERSISTENCE & STORAGE ---
    function initApp() {
      // Load stored students or default seed
      const saved = localStorage.getItem('kits_students_v02');
      if (saved) {
        try {
          students = JSON.parse(saved);
        } catch(e) {
          students = [...INITIAL_STUDENTS];
        }
      } else {
        students = [...INITIAL_STUDENTS];
        localStorage.setItem('kits_students_v02', JSON.stringify(students));
      }

      // Load stored authentication
      const savedUser = localStorage.getItem('kits_auth_v02');
      if (savedUser) {
        try {
          currentUser = JSON.parse(savedUser);
        } catch(e) {}
      } else {
        localStorage.setItem('kits_auth_v02', JSON.stringify(currentUser));
      }

      updateUserUI();
      setupTabs();
      setupEventListeners();
      renderAll();
      initMap();
    }

    function saveStudents() {
      localStorage.setItem('kits_students_v02', JSON.stringify(students));
      renderAll();
      if (leafletMap) updateMapMarkers();
    }

    function updateUserUI() {
      document.getElementById('user-display-name').textContent = currentUser.name;
      const roleBadge = document.getElementById('user-role-badge');
      roleBadge.textContent = currentUser.role.toUpperCase();
      
      if (currentUser.role === 'admin') {
        roleBadge.className = 'px-1.5 py-0.5 text-[9px] rounded uppercase font-extrabold bg-blue-500/20 text-blue-400 border border-blue-500/30';
      } else {
        roleBadge.className = 'px-1.5 py-0.5 text-[9px] rounded uppercase font-extrabold bg-amber-500/20 text-amber-400 border border-amber-500/30';
      }

      document.getElementById('login-btn-text').textContent = 'Switch Account';
      renderStudentTable();
    }

    // --- TABS MANAGEMENT ---
    function setupTabs() {
      const tabs = document.querySelectorAll('.nav-tab');
      tabs.forEach(tab => {
        tab.addEventListener('click', () => {
          const targetID = tab.getAttribute('data-tab');
          
          document.querySelectorAll('.nav-tab').forEach(t => {
            t.classList.remove('border-blue-500', 'text-blue-400');
            t.classList.add('border-transparent', 'text-slate-400');
          });
          tab.classList.remove('border-transparent', 'text-slate-400');
          tab.classList.add('border-blue-500', 'text-blue-400');

          document.querySelectorAll('.tab-content').forEach(c => c.classList.add('hidden'));
          document.getElementById(targetID).classList.remove('hidden');

          if (targetID === 'tab-map' && leafletMap) {
            setTimeout(() => leafletMap.invalidateSize(), 200);
          }
        });
      });
    }

    // --- RENDER ALL UI COMPONENTS ---
    function renderAll() {
      renderMetrics();
      renderCharts();
      renderDistanceBands();
      renderStudentTable();
      renderNAACReport();
    }

    function renderMetrics() {
      const total = students.length;
      document.getElementById('total-student-badge').textContent = `Total Students: ${total}`;

      let counts = { Local: 0, District: 0, 'Within State': 0, 'Other State': 0, International: 0 };
      
      students.forEach(s => {
        const cat = classifyLocality(s);
        if (counts[cat] !== undefined) counts[cat]++;
      });

      ['local', 'district', 'state', 'otherstate', 'intl'].forEach((key, idx) => {
        const catName = Object.keys(counts)[idx];
        const count = counts[catName];
        const pct = total > 0 ? ((count / total) * 100).toFixed(1) : 0;
        
        document.getElementById(`count-${key}`).textContent = count;
        document.getElementById(`pct-${key}`).textContent = `${pct}%`;
      });

      const outStateCount = counts['Other State'] + counts['International'];
      const outStatePct = total > 0 ? ((outStateCount / total) * 100).toFixed(1) : 0;
      const intlPct = total > 0 ? ((counts['International'] / total) * 100).toFixed(1) : 0;

      document.getElementById('stat-out-state-pct').textContent = `${outStatePct}%`;
      document.getElementById('stat-intl-pct').textContent = `${intlPct}%`;
    }

    function renderDistanceBands() {
      let r25 = 0, r150 = 0, r800 = 0, rFar = 0;

      students.forEach(s => {
        const dist = calculateDistance(CAMPUS.lat, CAMPUS.lng, s.lat, s.lng);
        if (dist <= 25) r25++;
        else if (dist <= 150) r150++;
        else if (dist <= 800) r800++;
        else rFar++;
      });

      document.getElementById('radius-25').textContent = r25;
      document.getElementById('radius-150').textContent = r150;
      document.getElementById('radius-800').textContent = r800;
      document.getElementById('radius-far').textContent = rFar;
    }

    function renderCharts() {
      let counts = { Local: 0, District: 0, 'Within State': 0, 'Other State': 0, International: 0 };
      let stateCounts = {};

      students.forEach(s => {
        const cat = classifyLocality(s);
        if (counts[cat] !== undefined) counts[cat]++;

        const st = s.state || 'Unknown';
        stateCounts[st] = (stateCounts[st] || 0) + 1;
      });

      // Donut Chart
      const donutCtx = document.getElementById('chart-locality-donut').getContext('2d');
      if (donutChartInstance) donutChartInstance.destroy();

      donutChartInstance = new Chart(donutCtx, {
        type: 'doughnut',
        data: {
          labels: Object.keys(counts),
          datasets: [{
            data: Object.values(counts),
            backgroundColor: ['#10b981', '#0ea5e9', '#f59e0b', '#f97316', '#ec4899'],
            borderWidth: 0
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: {
              position: 'bottom',
              labels: { color: '#cbd5e1', boxWidth: 12, font: { size: 11 } }
            }
          }
        }
      });

      // Bar Chart: Top States
      const sortedStates = Object.entries(stateCounts).sort((a,b) => b[1] - a[1]).slice(0, 6);
      const barCtx = document.getElementById('chart-states-bar').getContext('2d');
      if (barChartInstance) barChartInstance.destroy();

      barChartInstance = new Chart(barCtx, {
        type: 'bar',
        data: {
          labels: sortedStates.map(x => x[0]),
          datasets: [{
            label: 'Student Count',
            data: sortedStates.map(x => x[1]),
            backgroundColor: '#3b82f6',
            borderRadius: 6
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          plugins: {
            legend: { display: false }
          },
          scales: {
            x: { ticks: { color: '#94a3b8', font: { size: 10 } }, grid: { display: false } },
            y: { ticks: { color: '#94a3b8', precision: 0 }, grid: { color: '#334155' } }
          }
        }
      });
    }

    function renderStudentTable() {
      const tbody = document.getElementById('student-table-body');
      const search = document.getElementById('search-input').value.toLowerCase();
      const filterCat = document.getElementById('filter-category').value;
      const isAdmin = currentUser.role === 'admin';

      tbody.innerHTML = '';

      const filtered = students.filter(s => {
        const cat = classifyLocality(s);
        const matchesSearch = s.name.toLowerCase().includes(search) || 
                              s.id.toLowerCase().includes(search) || 
                              s.city.toLowerCase().includes(search) || 
                              s.district.toLowerCase().includes(search) ||
                              s.state.toLowerCase().includes(search);
        const matchesCat = filterCat === 'All' || cat === filterCat;
        return matchesSearch && matchesCat;
      });

      if (filtered.length === 0) {
        tbody.innerHTML = `<tr><td colspan="5" class="p-6 text-center text-slate-400">No student records found matching filter criteria.</td></tr>`;
        return;
      }

      filtered.forEach(s => {
        const cat = classifyLocality(s);
        const dist = calculateDistance(CAMPUS.lat, CAMPUS.lng, s.lat, s.lng).toFixed(1);
        const badgeCls = getBadgeClass(cat);

        const row = document.createElement('tr');
        row.className = 'hover:bg-slate-900/50 transition';
        row.innerHTML = `
          <td class="p-3">
            <div class="font-bold text-white">${s.name}</div>
            <div class="text-[10px] text-slate-400 font-mono">${s.id} • ${s.program}</div>
          </td>
          <td class="p-3">
            <div class="text-slate-200">${s.city}, ${s.district}</div>
            <div class="text-[10px] text-slate-400">${s.state}, ${s.country}</div>
          </td>
          <td class="p-3 font-mono text-slate-300">
            ${dist} km
          </td>
          <td class="p-3">
            <span class="px-2 py-0.5 text-[10px] font-bold rounded-full border ${badgeCls}">${cat}</span>
          </td>
          <td class="p-3 text-right space-x-2">
            <button onclick="editStudent('${s.id}')" class="px-2.5 py-1 ${isAdmin ? 'bg-slate-700 hover:bg-slate-600 text-slate-200' : 'bg-slate-800 text-slate-500 cursor-not-allowed'} rounded text-[11px] font-semibold transition">Edit</button>
            <button onclick="deleteStudent('${s.id}')" class="px-2.5 py-1 ${isAdmin ? 'bg-rose-900/40 hover:bg-rose-800 text-rose-300' : 'bg-slate-800 text-slate-600 cursor-not-allowed'} rounded text-[11px] font-semibold transition">Delete</button>
          </td>
        `;
        tbody.appendChild(row);
      });
    }

    function renderNAACReport() {
      const tbody = document.getElementById('naac-table-body');
      tbody.innerHTML = '';
      const total = students.length;

      let counts = { Local: 0, District: 0, 'Within State': 0, 'Other State': 0, International: 0 };
      students.forEach(s => {
        const cat = classifyLocality(s);
        if (counts[cat] !== undefined) counts[cat]++;
      });

      const metricsMap = {
        'Local': 'NAAC 2.1.1 (Surathkal Local Radius)',
        'District': 'NAAC 2.1.1 (Dakshina Kannada District)',
        'Within State': 'NAAC 2.1.1 & NIRF State Share',
        'Other State': 'NAAC 2.1.2 & NIRF Out-of-State ($P_{OS}$)',
        'International': 'NIRF Out-of-Country ($P_{OC}$)'
      };

      Object.entries(counts).forEach(([cat, count]) => {
        const pct = total > 0 ? ((count / total) * 100).toFixed(2) : 0;
        const row = document.createElement('tr');
        row.className = 'hover:bg-slate-900/50';
        row.innerHTML = `
          <td class="p-3 border-r border-slate-800 font-bold text-white">${cat}</td>
          <td class="p-3 border-r border-slate-800 text-slate-400">Institutional Geo-Scope Tier</td>
          <td class="p-3 border-r border-slate-800 text-center font-bold text-blue-400">${count}</td>
          <td class="p-3 border-r border-slate-800 text-center text-emerald-400">${pct}%</td>
          <td class="p-3 text-slate-300">${metricsMap[cat]}</td>
        `;
        tbody.appendChild(row);
      });
    }

    // --- LEAFLET MAP INITIALIZATION ---
    function initMap() {
      if (leafletMap) return;

      leafletMap = L.map('leaflet-map-container').setView([CAMPUS.lat, CAMPUS.lng], 9);

      L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png', {
        attribution: '&copy; <a href="https://carto.com/">CARTO</a> | KITS GIS Intelligence',
        maxZoom: 19
      }).addTo(leafletMap);

      // Campus Marker
      const campusIcon = L.divIcon({
        className: 'custom-campus-marker',
        html: `<div style="background:#2563eb; color:white; font-weight:800; padding:6px 10px; border-radius:8px; border:2px solid #ffffff; font-size:11px; white-space:nowrap; box-shadow:0 4px 12px rgba(37,99,235,0.4);">🏫 KITS Campus</div>`,
        iconSize: [100, 36],
        iconAnchor: [50, 18]
      });

      L.marker([CAMPUS.lat, CAMPUS.lng], { icon: campusIcon }).addTo(leafletMap)
        .bindPopup(`<b>${CAMPUS.name}</b><br>Reference Campus (Surathkal, Mangaluru)`);

      markersLayer = L.layerGroup().addTo(leafletMap);
      updateMapMarkers();
    }

    function updateMapMarkers() {
      if (!markersLayer) return;
      markersLayer.clearLayers();

      students.forEach(s => {
        const cat = classifyLocality(s);
        const color = getMarkerColor(cat);
        const dist = calculateDistance(CAMPUS.lat, CAMPUS.lng, s.lat, s.lng).toFixed(1);

        const circleIcon = L.divIcon({
          className: 'custom-student-marker',
          html: `<div style="background:${color}; width:14px; height:14px; border-radius:50%; border:2px solid #ffffff; box-shadow:0 2px 8px rgba(0,0,0,0.4);"></div>`,
          iconSize: [14, 14],
          iconAnchor: [7, 7]
        });

        const marker = L.marker([s.lat, s.lng], { icon: circleIcon });
        marker.bindPopup(`
          <div style="font-size:11px; line-height:1.4;">
            <strong style="color:#ffffff; font-size:12px;">${s.name}</strong><br>
            <span style="color:#94a3b8;">${s.id} • ${s.program}</span><br>
            📍 ${s.city}, ${s.state} (${cat})<br>
            📏 Distance to Campus: <b>${dist} km</b>
          </div>
        `);
        markersLayer.addLayer(marker);
      });
    }

    // --- FORM & CRUD ACTIONS ---
    window.editStudent = function(id) {
      if (currentUser.role !== 'admin') {
        showToast('Access Denied: Only authenticated administrators can modify student records.', 'error');
        document.getElementById('login-modal').classList.remove('hidden');
        return;
      }

      const s = students.find(x => x.id === id);
      if (!s) return;

      document.getElementById('edit-id').value = s.id;
      document.getElementById('name').value = s.name;
      document.getElementById('program').value = s.program;
      document.getElementById('city').value = s.city;
      document.getElementById('district').value = s.district;
      document.getElementById('state').value = s.state;
      document.getElementById('country').value = s.country;

      document.getElementById('form-title').textContent = `Edit Student: ${s.id}`;
      document.getElementById('form-mode-badge').textContent = 'EDIT';
      document.getElementById('form-mode-badge').className = 'text-[10px] bg-amber-500/20 text-amber-300 border border-amber-500/30 px-2 py-0.5 rounded font-mono';
      document.getElementById('form-submit-btn').textContent = 'Update Student Record';
      document.getElementById('form-cancel-btn').classList.remove('hidden');

      // Switch to student tab if not active
      document.querySelector('[data-tab="tab-students"]').click();
    };

    window.deleteStudent = function(id) {
      if (currentUser.role !== 'admin') {
        showToast('Access Denied: Only authenticated administrators can delete student records.', 'error');
        document.getElementById('login-modal').classList.remove('hidden');
        return;
      }

      if (confirm(`Are you sure you want to delete student ID ${id}?`)) {
        students = students.filter(x => x.id !== id);
        saveStudents();
        showToast(`Student ${id} deleted successfully.`, 'success');
      }
    };

    function resetForm() {
      document.getElementById('edit-id').value = '';
      document.getElementById('student-form').reset();
      document.getElementById('country').value = 'India';
      document.getElementById('program').value = 'B.Tech CSE';
      document.getElementById('form-title').textContent = 'Add New Student Record';
      document.getElementById('form-mode-badge').textContent = 'NEW';
      document.getElementById('form-mode-badge').className = 'text-[10px] bg-blue-500/20 text-blue-300 border border-blue-500/30 px-2 py-0.5 rounded font-mono';
      document.getElementById('form-submit-btn').textContent = 'Create & Auto-Classify Location';
      document.getElementById('form-cancel-btn').classList.add('hidden');
    }

    // --- EVENT LISTENERS & INTERACTIONS ---
    function setupEventListeners() {
      // Form Submission
      document.getElementById('student-form').addEventListener('submit', (e) => {
        e.preventDefault();
        if (currentUser.role !== 'admin') {
          showToast('Access Denied: Only verified administrators can add or update records.', 'error');
          document.getElementById('login-modal').classList.remove('hidden');
          return;
        }

        const editId = document.getElementById('edit-id').value;
        const name = document.getElementById('name').value.trim();
        const program = document.getElementById('program').value.trim();
        const city = document.getElementById('city').value.trim();
        const district = document.getElementById('district').value.trim();
        const state = document.getElementById('state').value.trim();
        const country = document.getElementById('country').value.trim();

        // Approximate realistic coords based on city or random offset from campus if unknown
        let lat = CAMPUS.lat + (Math.random() - 0.5) * 2;
        let lng = CAMPUS.lng + (Math.random() - 0.5) * 2;

        const cityLower = city.toLowerCase();
        if (cityLower === 'surathkal') { lat = 13.012; lng = 74.795; }
        else if (cityLower === 'mangaluru') { lat = 12.914; lng = 74.856; }
        else if (cityLower === 'udupi') { lat = 13.340; lng = 74.742; }
        else if (cityLower === 'bengaluru') { lat = 12.971; lng = 77.594; }
        else if (cityLower === 'mumbai') { lat = 19.076; lng = 72.877; }
        else if (cityLower === 'delhi') { lat = 28.613; lng = 77.209; }

        if (editId) {
          const idx = students.findIndex(x => x.id === editId);
          if (idx !== -1) {
            students[idx] = { ...students[idx], name, program, city, district, state, country, lat, lng };
            showToast(`Student ${editId} updated successfully!`, 'success');
          }
        } else {
          const newId = `KITS-2026-${String(students.length + 101).padStart(3, '0')}`;
          students.push({ id: newId, name, program, city, district, state, country, lat, lng });
          showToast(`New student ${newId} added & classified!`, 'success');
        }

        saveStudents();
        resetForm();
      });

      document.getElementById('form-cancel-btn').addEventListener('click', resetForm);

      // Search & Filter
      document.getElementById('search-input').addEventListener('input', renderStudentTable);
      document.getElementById('filter-category').addEventListener('change', renderStudentTable);

      // Quick Batch Generators
      document.getElementById('btn-gen-10').addEventListener('click', () => {
        if (currentUser.role !== 'admin') { showToast('Access Denied: Admin password required.', 'error'); document.getElementById('login-modal').classList.remove('hidden'); return; }
        generateRandomBatch(10);
      });
      document.getElementById('btn-gen-25').addEventListener('click', () => {
        if (currentUser.role !== 'admin') { showToast('Access Denied: Admin password required.', 'error'); document.getElementById('login-modal').classList.remove('hidden'); return; }
        generateRandomBatch(25);
      });

      // Export JSON
      document.getElementById('btn-export').addEventListener('click', () => {
        const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(students, null, 2));
        const dlAnchor = document.createElement('a');
        dlAnchor.setAttribute("href", dataStr);
        dlAnchor.setAttribute("download", `KITS_Student_Locality_Export_${new Date().toISOString().slice(0,10)}.json`);
        document.body.appendChild(dlAnchor);
        dlAnchor.click();
        dlAnchor.remove();
        showToast('Student database exported as JSON successfully.', 'success');
      });

      // Import JSON Trigger
      document.getElementById('btn-import-trigger').addEventListener('click', () => {
        if (currentUser.role !== 'admin') { showToast('Access Denied: Admin password required.', 'error'); document.getElementById('login-modal').classList.remove('hidden'); return; }
        document.getElementById('import-file').click();
      });

      document.getElementById('import-file').addEventListener('change', (e) => {
        const file = e.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = function(evt) {
          try {
            const imported = JSON.parse(evt.target.result);
            if (Array.isArray(imported)) {
              students = imported;
              saveStudents();
              showToast(`Successfully imported ${imported.length} student records!`, 'success');
            } else {
              showToast('Invalid JSON file format.', 'error');
            }
          } catch(err) {
            showToast('Failed to parse JSON file.', 'error');
          }
        };
        reader.readAsText(file);
      });

      // Reset Demo Modal
      document.getElementById('btn-prompt-reset').addEventListener('click', () => {
        if (currentUser.role !== 'admin') { showToast('Access Denied: Admin password required.', 'error'); document.getElementById('login-modal').classList.remove('hidden'); return; }
        document.getElementById('reset-modal').classList.remove('hidden');
      });
      document.getElementById('btn-modal-cancel').addEventListener('click', () => {
        document.getElementById('reset-modal').classList.add('hidden');
      });
      document.getElementById('btn-modal-confirm').addEventListener('click', () => {
        students = [...INITIAL_STUDENTS];
        saveStudents();
        document.getElementById('reset-modal').classList.add('hidden');
        showToast('Database reset to default 30 sample students.', 'success');
      });

      // Sync Modal
      document.getElementById('btn-sync-settings').addEventListener('click', () => {
        document.getElementById('sync-modal').classList.remove('hidden');
      });
      document.getElementById('btn-sync-close').addEventListener('click', () => {
        document.getElementById('sync-modal').classList.add('hidden');
      });
      document.getElementById('btn-sync-modal-cancel').addEventListener('click', () => {
        document.getElementById('sync-modal').classList.add('hidden');
      });
      document.getElementById('btn-save-sync').addEventListener('click', () => {
        document.getElementById('sync-modal').classList.add('hidden');
        showToast('Cloud database sync channel linked successfully!', 'success');
      });

      // Copy NAAC Report
      document.getElementById('btn-copy-report').addEventListener('click', () => {
        const table = document.getElementById('naac-report-table');
        let text = "";
        for (let row of table.rows) {
          let cols = Array.from(row.cells).map(c => c.innerText.trim());
          text += cols.join("\t") + "\n";
        }
        navigator.clipboard.writeText(text).then(() => {
          showToast('NAAC / NIRF report matrix copied to clipboard!', 'success');
        });
      });

      // Login Modal Controls
      document.getElementById('btn-open-login').addEventListener('click', () => {
        document.getElementById('login-password').value = '';
        document.getElementById('login-modal').classList.remove('hidden');
      });
      document.getElementById('btn-login-close').addEventListener('click', () => {
        document.getElementById('login-modal').classList.add('hidden');
      });

      // Admin preset buttons inside login modal
      document.querySelectorAll('.admin-preset-btn').forEach(btn => {
        btn.addEventListener('click', () => {
          document.querySelectorAll('.admin-preset-btn').forEach(b => {
            b.className = 'admin-preset-btn p-2 rounded-xl border border-slate-800 bg-slate-950/60 text-slate-400 hover:border-slate-700 text-center transition flex flex-col items-center gap-1';
          });
          btn.className = 'admin-preset-btn p-2 rounded-xl border border-blue-500 bg-blue-500/10 text-blue-400 text-center transition flex flex-col items-center gap-1';
          
          const adminName = btn.getAttribute('data-admin');
          const role = btn.getAttribute('data-role');
          document.getElementById('login-selected-admin').value = adminName;
          document.getElementById('login-selected-role').value = role;
          
          const nameInputContainer = document.getElementById('name-input-container');
          const passwordContainer = document.getElementById('password-field-container');
          const customNameInput = document.getElementById('login-custom-name');
          const nameInputLabel = document.getElementById('name-input-label');

          if (role === 'admin') {
            passwordContainer.style.display = 'block';
            nameInputContainer.style.display = 'none';
          } else if (role === 'student') {
            passwordContainer.style.display = 'none';
            nameInputContainer.style.display = 'block';
            nameInputLabel.textContent = 'Enter Student Name';
            customNameInput.value = '';
            customNameInput.placeholder = 'e.g. Aarav Shetty';
          } else if (role === 'faculty') {
            passwordContainer.style.display = 'none';
            nameInputContainer.style.display = 'block';
            nameInputLabel.textContent = 'Enter Faculty Name';
            customNameInput.value = '';
            customNameInput.placeholder = 'e.g. Dr. Ramesh Rao';
          }
        });
      });

      document.getElementById('login-form').addEventListener('submit', (e) => {
        e.preventDefault();
        let adminName = document.getElementById('login-selected-admin').value;
        const role = document.getElementById('login-selected-role').value;
        const password = document.getElementById('login-password').value;

        if (role === 'admin') {
          if (password !== 'admin@123') {
            showToast('Incorrect password. Please try again.', 'error');
            return;
          }
        } else {
          const customNameInput = document.getElementById('login-custom-name').value.trim();
          if (customNameInput) {
            adminName = customNameInput;
          } else {
            showToast('Please enter your name.', 'error');
            return;
          }
        }

        currentUser = { name: adminName, email: `${adminName.toLowerCase().replace(/\s+/g, '')}@kits.edu.in`, role: role === 'admin' ? 'admin' : 'viewer' };
        localStorage.setItem('kits_auth_v02', JSON.stringify(currentUser));
        updateUserUI();
        document.getElementById('login-modal').classList.add('hidden');
        showToast(`Successfully signed in as ${role.toUpperCase()}: ${adminName}`, 'success');
        renderStudentTable();
      });
    }

    function generateRandomBatch(count) {
      const firstNames = ["Aarav", "Vivaan", "Aditya", "Vihaan", "Arjun", "Sai", "Reyansh", "Ayaan", "Krishna", "Ishaan", "Ananya", "Aadhya", "Diya", "Sana", "Pari", "Riya", "Anika", "Navya", "Pooja", "Meera"];
      const lastNames = ["Shetty", "Rao", "Kamath", "Hegde", "Pai", "Naik", "Suvarna", "Bhat", "Acharya", "Nayak", "Verma", "Sharma", "Gupta", "Patel", "Reddy", "Nair", "Menon", "Iyer", "Deshmukh", "Kulkarni"];
      const programs = ["B.Tech CSE", "B.Tech ECE", "B.Tech AI & DS", "B.Tech Mechanical", "B.Tech Civil", "B.Tech EEE"];
      const citiesPool = [
        { city: "Surathkal", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 13.012, lng: 74.793 },
        { city: "Mangaluru", district: "Dakshina Kannada", state: "Karnataka", country: "India", lat: 12.914, lng: 74.856 },
        { city: "Udupi", district: "Udupi", state: "Karnataka", country: "India", lat: 13.340, lng: 74.742 },
        { city: "Bengaluru", district: "Bengaluru Urban", state: "Karnataka", country: "India", lat: 12.971, lng: 77.594 },
        { city: "Mysuru", district: "Mysuru", state: "Karnataka", country: "India", lat: 12.295, lng: 76.639 },
        { city: "Kochi", district: "Ernakulam", state: "Kerala", country: "India", lat: 9.931, lng: 76.267 },
        { city: "Mumbai", district: "Mumbai Suburban", state: "Maharashtra", country: "India", lat: 19.076, lng: 72.877 },
        { city: "Chennai", district: "Chennai", state: "Tamil Nadu", country: "India", lat: 13.082, lng: 80.270 },
        { city: "Hyderabad", district: "Hyderabad", state: "Telangana", country: "India", lat: 17.385, lng: 78.486 },
        { city: "Singapore", district: "Singapore Central", state: "Singapore", country: "Singapore", lat: 1.352, lng: 103.819 }
      ];

      for (let i = 0; i < count; i++) {
        const fn = firstNames[Math.floor(Math.random() * firstNames.length)];
        const ln = lastNames[Math.floor(Math.random() * lastNames.length)];
        const prog = programs[Math.floor(Math.random() * programs.length)];
        const loc = citiesPool[Math.floor(Math.random() * citiesPool.length)];
        const newId = `KITS-2026-${String(students.length + 101).padStart(3, '0')}`;

        students.push({
          id: newId,
          name: `${fn} ${ln}`,
          program: prog,
          city: loc.city,
          district: loc.district,
          state: loc.state,
          country: loc.country,
          lat: loc.lat + (Math.random() - 0.5) * 0.05,
          lng: loc.lng + (Math.random() - 0.5) * 0.05
        });
      }

      saveStudents();
      showToast(`Generated and classified ${count} sample student records!`, 'success');
    }

    // Run initialization on DOM load
    document.addEventListener('DOMContentLoaded', initApp);
  </script>
</body>
</html>
