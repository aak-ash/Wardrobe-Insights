<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Wardrobe Insights</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: 'Inter', sans-serif;
    }
    .form-container {
      max-width: 800px;
      background: linear-gradient(145deg, #ffffff, #f0f4f8);
      border-radius: 16px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
    }
    .input-field, .select-field {
      transition: all 0.3s ease;
    }
    .input-field:focus, .select-field:focus {
      border-color: #3b82f6;
      box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
    }
    .section-title {
      border-bottom: 2px solid #e5e7eb;
    }
    .error-message {
      animation: fadeIn 0.3s ease-in;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body class="bg-gray-50 min-h-screen flex items-center justify-center p-4">
  <div class="form-container mx-auto p-8">
    <h1 class="text-3xl font-bold text-gray-800 mb-4 text-center">Wardrobe Insights</h1>
    <p class="text-gray-600 mb-6 text-center">Please share your responses. All fields marked with * are required. Responses are confidential.</p>
    <form id="surveyForm" class="space-y-8">
      <!-- Demographics -->
      <div class="mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Personal Information</h2>
        <div class="space-y-4">
          <div>
            <label class="block text-sm font-medium text-gray-700">Name *</label>
            <input type="text" name="Name" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Email *</label>
            <input type="email" name="Email" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Age *</label>
            <select name="Age" class="select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
              <option value="">Select age range</option>
              <option value="18-25">18–25</option>
              <option value="26-30">26–30</option>
              <option value="31-35">31–35</option>
              <option value="36-40">36–40</option>
            </select>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">City *</label>
            <input type="text" name="City" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
        </div>
      </div>

      <!-- Wardrobe Split -->
      <div class="mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Wardrobe Composition</h2>
        <p class="text-sm font-medium text-gray-600 mb-3">Estimate the percentage of your wardrobe for each category (total must sum to 100%): *</p>
        <div class="space-y-4">
          <div>
            <label class="block text-sm font-medium text-gray-700">Going out/Partywear (%)</label>
            <input type="number" name="Wardrobe_Going_out" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Casual Wear (%)</label>
            <input type="number" name="Wardrobe_Casual" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Formals/Semi-formals (%)</label>
            <input type="number" name="Wardrobe_Formals" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Ethnic/Indo-western (%)</label>
            <input type="number" name="Wardrobe_Ethnic" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Others (incl. Nightwear) (%)</label>
            <input type="number" name="Wardrobe_Others" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
        </div>
        <p class="text-red-500 text-sm mt-2 hidden wardrobe-error">Percentages must sum to 100%.</p>
      </div>

      <!-- Category: Going out/Partywear -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Going out/Partywear</h2>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a range for each channel; distribution should approximate 100%): *</p>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Platforms like Myntra</label>
              <select name="Going_out_Myntra" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Brand Website</label>
              <select name="Going_out_Brand_Website" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">D2C/Social Media</label>
              <select name="Going_out_D2C" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Offline Shops</label>
              <select name="Going_out_Offline" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Unorganized/Thrifted</label>
              <select name="Going_out_Thrifted" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel distributions should approximate 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">List up to 5 brands you frequently buy for Going out/Partywear:</p>
          <div class="space-y-3">
            <input type="text" name="Going_out_Brand1" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Category: Casual Wear -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Casual Wear</h2>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a range for each channel; distribution should approximate 100%): *</p>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Platforms like Myntra</label>
              <select name="Casual_Myntra" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Brand Website</label>
              <select name="Casual_Brand_Website" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">D2C/Social Media</label>
              <select name="Casual_D2C" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Offline Shops</label>
              <select name="Casual_Offline" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Unorganized/Thrifted</label>
              <select name="Casual_Thrifted" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel distributions should approximate 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">List up to 5 brands you frequently buy for Casual Wear:</p>
          <div class="space-y-3">
            <input type="text" name="Casual_Brand1" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Casual_Brand2" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Casual_Brand3" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Casual_Brand4" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Casual_Brand5" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Category: Formals/Semi-formals -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Formals/Semi-formals</h2>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a range for each channel; distribution should approximate 100%): *</p>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Platforms like Myntra</label>
              <select name="Formals_Myntra" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Brand Website</label>
              <select name="Formals_Brand_Website" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">D2C/Social Media</label>
              <select name="Formals_D2C" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Offline Shops</label>
              <select name="Formals_Offline" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Unorganized/Thrifted</label>
              <select name="Formals_Thrifted" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel distributions should approximate 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">List up to 5 brands you frequently buy for Formals/Semi-formals:</p>
          <div class="space-y-3">
            <input type="text" name="Formals_Brand1" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Formals_Brand2" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Formals_Brand3" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Formals_Brand4" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Formals_Brand5" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Category: Ethnic/Indo-western -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Ethnic/Indo-western</h2>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a range for each channel; distribution should approximate 100%): *</p>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Platforms like Myntra</label>
              <select name="Ethnic_Myntra" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Brand Website</label>
              <select name="Ethnic_Brand_Website" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">D2C/Social Media</label>
              <select name="Ethnic_D2C" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Offline Shops</label>
              <select name="Ethnic_Offline" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Unorganized/Thrifted</label>
              <select name="Ethnic_Thrifted" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel distributions should approximate 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">List up to 5 brands you frequently buy for Ethnic/Indo-western:</p>
          <div class="space-y-3">
            <input type="text" name="Ethnic_Brand1" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Ethnic_Brand2" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Ethnic_Brand3" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Ethnic_Brand4" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Ethnic_Brand5" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Category: Others (incl. Nightwear) -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Others (incl. Nightwear)</h2>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a range for each channel; distribution should approximate 100%): *</p>
          <div class="space-y-4">
            <div>
              <label class="block text-sm font-medium text-gray-700">Platforms like Myntra</label>
              <select name="Others_Myntra" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Brand Website</label>
              <select name="Others_Brand_Website" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">D2C/Social Media</label>
              <select name="Others_D2C" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Offline Shops</label>
              <select name="Others_Offline" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700">Unorganized/Thrifted</label>
              <select name="Others_Thrifted" class="percent select-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
                <option value="5">0–10%</option>
                <option value="17.5">10%–25%</option>
                <option value="32.5">25%–40%</option>
                <option value="50">40%–60%</option>
                <option value="70">60%–80%</option>
                <option value="90">80%–100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel distributions should approximate 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">List up to 5 brands you frequently buy for Others (incl. Nightwear):</p>
          <div class="space-y-3">
            <input type="text" name="Others_Brand1" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Others_Brand2" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Others_Brand3" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Others_Brand4" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Others_Brand5" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <div class="text-center">
        <button type="submit" id="submitBtn" class="bg-blue-600 text-white px-8 py-3 rounded-lg hover:bg-blue-700 transition duration-300">Submit</button>
      </div>
    </form>
  </div>

  <script>
    const form = document.getElementById('surveyForm');
    const scriptURL = 'https://script.google.com/macros/s/AKfycbx18pbpszswuA-WvrwaZZy8-GWHTU1v_1zsZi-BHmopMYGrLuP3_E7lPQq3RcVSeHEU/exec'; // You've updated this with your Google Apps Script URL

    // Validate wardrobe percentages (must sum to 100%)
    function validateWardrobe() {
      const inputs = document.querySelectorAll('.wardrobe-percent');
      let sum = 0;
      inputs.forEach(input => {
        sum += parseInt(input.value) || 0;
      });
      const errorMessage = document.querySelector('.wardrobe-error');
      if (sum !== 100) {
        errorMessage.classList.remove('hidden');
        return false;
      } else {
        errorMessage.classList.add('hidden');
        return true;
      }
    }

    // Validate category channel distributions (sum of midpoints should approximate 100%)
    function validateCategoryPercentages(categoryDiv) {
      const selects = categoryDiv.querySelectorAll('.percent');
      let sum = 0;
      selects.forEach(select => {
        sum += parseFloat(select.value);
      });
      const errorMessage = categoryDiv.querySelector('.error-message');
      // Allow some flexibility due to ranges (sum between 80 and 120)
      if (sum < 80 || sum > 120) {
        errorMessage.classList.remove('hidden');
        return false;
      } else {
        errorMessage.classList.add('hidden');
        return true;
      }
    }

    // Validate entire form
    function validateForm() {
      let isValid = validateWardrobe();
      const categories = document.querySelectorAll('.category');
      categories.forEach(category => {
        if (!validateCategoryPercentages(category)) {
          isValid = false;
        }
      });
      return isValid;
    }

    // Handle form submission
    form.addEventListener('submit', e => {
      e.preventDefault();
      if (validateForm()) {
        fetch(scriptURL, {
          method: 'POST',
          body: new FormData(form)
        })
        .then(response => response.json())
        .then(data => {
          if (data.result === 'success') {
            alert('Thank you! Your responses have been submitted.');
            form.reset();
          } else {
            alert('Error submitting form: ' + data.error);
          }
        })
        .catch(error => {
          console.error('Error!', error.message);
          alert('Error submitting form. Please try again.');
        });
      } else {
        alert('Please ensure wardrobe percentages sum to 100% and channel distributions approximate 100%.');
      }
    });
  </script>
</body>
</html>
