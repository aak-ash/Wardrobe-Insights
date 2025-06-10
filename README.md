
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fashion Survey Wardrobe Insights</title>
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
    th, td {
      text-align: center;
      padding: 8px;
      border: 1px solid #e5e7eb;
    }
    th {
      background-color: #f9fafb;
      font-weight: 600;
      color: #374151;
    }
    td:first-child {
      text-align: left;
      font-weight: 500;
    }
    @media (max-width: 640px) {
      th, td {
        display: block;
        width: 100%;
        text-align: left;
        border: none;
        border-bottom: 1px solid #e5e7eb;
      }
      th {
        background-color: #f3f4f6;
      }
      tr {
        display: block;
        margin-bottom: 1rem;
      }
      table {
        border: none;
      }
      td:first-child {
        font-weight: 600;
        background-color: #f9fafb;
      }
    }
  </style>
</head>
<body class="bg-gray-50 min-h-screen flex items-center justify-center p-4">
  <div class="form-container mx-auto p-8">
    <h1 class="text-3xl font-bold text-gray-800 mb-4 text-center">Fashion Survey - Wardrobe Insights</h1>
    <p class="text-gray-600 mb-6 text-center">Share your shopping habits, favorite brands, and wardrobe vibes in this quick survey. All fields marked with * are required, and your responses are 100% confidential.</p>
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
            <label class="block text-sm font-medium text-gray-700">Going out/Partywear (%) <span class="text-sm text-gray-600">(Special occasion statement pieces, e.g., cocktail dresses, tuxedos)</span></label>
            <input type="number" name="Wardrobe_Going_out" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Casual Wear (%) <span class="text-sm text-gray-600">(Everyday informal wear, including loungewear, e.g., t-shirts, jeans)</span></label>
            <input type="number" name="Wardrobe_Casual" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Formals/Semi-formals (%) <span class="text-sm text-gray-600">(Professional or business attire, e.g., suits, blazers)</span></label>
            <input type="number" name="Wardrobe_Formals" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Ethnic/Indo-western (%) <span class="text-sm text-gray-600">(Traditional or fusion cultural wear, e.g., sarees, kurtas)</span></label>
            <input type="number" name="Wardrobe_Ethnic" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700">Others (incl. Nightwear) (%) <span class="text-sm text-gray-600">(Nightwear, gym wear, or specialty items, e.g., pajamas, athletic wear)</span></label>
            <input type="number" name="Wardrobe_Others" min="0" max="100" class="wardrobe-percent input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
          </div>
        </div>
        <p class="text-red-500 text-sm mt-2 hidden wardrobe-error">Percentages must sum to 100%.</p>
      </div>

      <!-- Category: Going out/Partywear -->
      <div class="category mb-6">
        <h2 class="text-xl font-semibold text-gray-700 mb-4 section-title pb-2">Going out/Partywear</h2>
        <p class="text-sm text-gray-600 mb-3">Clothing designed for special occasions like parties, functions, or fancy dinners, where you wear statement pieces to stand out (e.g., cocktail dresses, tuxedos, sequined outfits).</p>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="overflow-x-auto">
            <table class="w-full table-auto border-collapse">
              <thead>
                <tr>
                  <th class="text-sm">Channel</th>
                  <th class="text-sm">0%</th>
                  <th class="text-sm">20%</th>
                  <th class="text-sm">40%</th>
                  <th class="text-sm">60%</th>
                  <th class="text-sm">80%</th>
                  <th class="text-sm">100%</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Platforms like Myntra/Ajio</td>
                  <td><input type="radio" name="Going_out_Platforms" value="0" class="percent" required></td>
                  <td><input type="radio" name="Going_out_Platforms" value="20" class="percent"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="40" class="percent"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="60" class="percent"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="80" class="percent"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="0" class="percent" required></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="20" class="percent"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="40" class="percent"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="60" class="percent"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="80" class="percent"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Going_out_D2C" value="0" class="percent" required></td>
                  <td><input type="radio" name="Going_out_D2C" value="20" class="percent"></td>
                  <td><input type="radio" name="Going_out_D2C" value="40" class="percent"></td>
                  <td><input type="radio" name="Going_out_D2C" value="60" class="percent"></td>
                  <td><input type="radio" name="Going_out_D2C" value="80" class="percent"></td>
                  <td><input type="radio" name="Going_out_D2C" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Going_out_Offline" value="0" class="percent" required></td>
                  <td><input type="radio" name="Going_out_Offline" value="20" class="percent"></td>
                  <td><input type="radio" name="Going_out_Offline" value="40" class="percent"></td>
                  <td><input type="radio" name="Going_out_Offline" value="60" class="percent"></td>
                  <td><input type="radio" name="Going_out_Offline" value="80" class="percent"></td>
                  <td><input type="radio" name="Going_out_Offline" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Going_out_Unorganised" value="0" class="percent" required></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="20" class="percent"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="40" class="percent"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="60" class="percent"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="80" class="percent"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="100" class="percent"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
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
        <p class="text-sm text-gray-600 mb-3">Everyday clothing for informal settings like travel, casual brunches, meeting friends, or lounging at home, prioritizing comfort and simplicity (e.g., t-shirts, jeans, sneakers, loungewear).</p>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="overflow-x-auto">
            <table class="w-full table-auto border-collapse">
              <thead>
                <tr>
                  <th class="text-sm">Channel</th>
                  <th class="text-sm">0%</th>
                  <th class="text-sm">20%</th>
                  <th class="text-sm">40%</th>
                  <th class="text-sm">60%</th>
                  <th class="text-sm">80%</th>
                  <th class="text-sm">100%</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Platforms like Myntra/Ajio</td>
                  <td><input type="radio" name="Casual_Platforms" value="0" class="percent" required></td>
                  <td><input type="radio" name="Casual_Platforms" value="20" class="percent"></td>
                  <td><input type="radio" name="Casual_Platforms" value="40" class="percent"></td>
                  <td><input type="radio" name="Casual_Platforms" value="60" class="percent"></td>
                  <td><input type="radio" name="Casual_Platforms" value="80" class="percent"></td>
                  <td><input type="radio" name="Casual_Platforms" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="0" class="percent" required></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="20" class="percent"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="40" class="percent"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="60" class="percent"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="80" class="percent"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Casual_D2C" value="0" class="percent" required></td>
                  <td><input type="radio" name="Casual_D2C" value="20" class="percent"></td>
                  <td><input type="radio" name="Casual_D2C" value="40" class="percent"></td>
                  <td><input type="radio" name="Casual_D2C" value="60" class="percent"></td>
                  <td><input type="radio" name="Casual_D2C" value="80" class="percent"></td>
                  <td><input type="radio" name="Casual_D2C" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Casual_Offline" value="0" class="percent" required></td>
                  <td><input type="radio" name="Casual_Offline" value="20" class="percent"></td>
                  <td><input type="radio" name="Casual_Offline" value="40" class="percent"></td>
                  <td><input type="radio" name="Casual_Offline" value="60" class="percent"></td>
                  <td><input type="radio" name="Casual_Offline" value="80" class="percent"></td>
                  <td><input type="radio" name="Casual_Offline" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Casual_Unorganised" value="0" class="percent" required></td>
                  <td><input type="radio" name="Casual_Unorganised" value="20" class="percent"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="40" class="percent"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="60" class="percent"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="80" class="percent"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="100" class="percent"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
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
        <p class="text-sm text-gray-600 mb-3">Professional or business-appropriate clothing for workplaces, meetings, or semi-formal events, typically structured and polished (e.g., suits, blazers, dress shirts).</p>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="overflow-x-auto">
            <table class="w-full table-auto border-collapse">
              <thead>
                <tr>
                  <th class="text-sm">Channel</th>
                  <th class="text-sm">0%</th>
                  <th class="text-sm">20%</th>
                  <th class="text-sm">40%</th>
                  <th class="text-sm">60%</th>
                  <th class="text-sm">80%</th>
                  <th class="text-sm">100%</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Platforms like Myntra/Ajio</td>
                  <td><input type="radio" name="Formals_Platforms" value="0" class="percent" required></td>
                  <td><input type="radio" name="Formals_Platforms" value="20" class="percent"></td>
                  <td><input type="radio" name="Formals_Platforms" value="40" class="percent"></td>
                  <td><input type="radio" name="Formals_Platforms" value="60" class="percent"></td>
                  <td><input type="radio" name="Formals_Platforms" value="80" class="percent"></td>
                  <td><input type="radio" name="Formals_Platforms" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="0" class="percent" required></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="20" class="percent"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="40" class="percent"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="60" class="percent"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="80" class="percent"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Formals_D2C" value="0" class="percent" required></td>
                  <td><input type="radio" name="Formals_D2C" value="20" class="percent"></td>
                  <td><input type="radio" name="Formals_D2C" value="40" class="percent"></td>
                  <td><input type="radio" name="Formals_D2C" value="60" class="percent"></td>
                  <td><input type="radio" name="Formals_D2C" value="80" class="percent"></td>
                  <td><input type="radio" name="Formals_D2C" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Formals_Offline" value="0" class="percent" required></td>
                  <td><input type="radio" name="Formals_Offline" value="20" class="percent"></td>
                  <td><input type="radio" name="Formals_Offline" value="40" class="percent"></td>
                  <td><input type="radio" name="Formals_Offline" value="60" class="percent"></td>
                  <td><input type="radio" name="Formals_Offline" value="80" class="percent"></td>
                  <td><input type="radio" name="Formals_Offline" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Formals_Unorganised" value="0" class="percent" required></td>
                  <td><input type="radio" name="Formals_Unorganised" value="20" class="percent"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="40" class="percent"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="60" class="percent"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="80" class="percent"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="100" class="percent"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
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
        <p class="text-sm text-gray-600 mb-3">Traditional or fusion clothing reflecting cultural heritage or modern adaptations, worn for festivals, weddings, or cultural events (e.g., sarees, kurtas, lehengas, Indo-western dresses).</p>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="overflow-x-auto">
            <table class="w-full table-auto border-collapse">
              <thead>
                <tr>
                  <th class="text-sm">Channel</th>
                  <th class="text-sm">0%</th>
                  <th class="text-sm">20%</th>
                  <th class="text-sm">40%</th>
                  <th class="text-sm">60%</th>
                  <th class="text-sm">80%</th>
                  <th class="text-sm">100%</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Platforms like Myntra/Ajio</td>
                  <td><input type="radio" name="Ethnic_Platforms" value="0" class="percent" required></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="20" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="40" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="60" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="80" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="0" class="percent" required></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="20" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="40" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="60" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="80" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Ethnic_D2C" value="0" class="percent" required></td>
                  <td><input type="radio" name="Ethnic_D2C" value="20" class="percent"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="40" class="percent"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="60" class="percent"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="80" class="percent"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Ethnic_Offline" value="0" class="percent" required></td>
                  <td><input type="radio" name="Ethnic_Offline" value="20" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="40" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="60" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="80" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="0" class="percent" required></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="20" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="40" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="60" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="80" class="percent"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="100" class="percent"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
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
        <p class="text-sm text-gray-600 mb-3">Miscellaneous clothing not covered by other categories, including nightwear, gym wear, or other specialty items (e.g., pajamas, athletic wear, costumes).</p>
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="overflow-x-auto">
            <table class="w-full table-auto border-collapse">
              <thead>
                <tr>
                  <th class="text-sm">Channel</th>
                  <th class="text-sm">0%</th>
                  <th class="text-sm">20%</th>
                  <th class="text-sm">40%</th>
                  <th class="text-sm">60%</th>
                  <th class="text-sm">80%</th>
                  <th class="text-sm">100%</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>Platforms like Myntra/Ajio</td>
                  <td><input type="radio" name="Others_Platforms" value="0" class="percent" required></td>
                  <td><input type="radio" name="Others_Platforms" value="20" class="percent"></td>
                  <td><input type="radio" name="Others_Platforms" value="40" class="percent"></td>
                  <td><input type="radio" name="Others_Platforms" value="60" class="percent"></td>
                  <td><input type="radio" name="Others_Platforms" value="80" class="percent"></td>
                  <td><input type="radio" name="Others_Platforms" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Others_Brand_Websites" value="0" class="percent" required></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="20" class="percent"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="40" class="percent"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="60" class="percent"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="80" class="percent"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Others_D2C" value="0" class="percent" required></td>
                  <td><input type="radio" name="Others_D2C" value="20" class="percent"></td>
                  <td><input type="radio" name="Others_D2C" value="40" class="percent"></td>
                  <td><input type="radio" name="Others_D2C" value="60" class="percent"></td>
                  <td><input type="radio" name="Others_D2C" value="80" class="percent"></td>
                  <td><input type="radio" name="Others_D2C" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Others_Offline" value="0" class="percent" required></td>
                  <td><input type="radio" name="Others_Offline" value="20" class="percent"></td>
                  <td><input type="radio" name="Others_Offline" value="40" class="percent"></td>
                  <td><input type="radio" name="Others_Offline" value="60" class="percent"></td>
                  <td><input type="radio" name="Others_Offline" value="80" class="percent"></td>
                  <td><input type="radio" name="Others_Offline" value="100" class="percent"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Others_Unorganised" value="0" class="percent" required></td>
                  <td><input type="radio" name="Others_Unorganised" value="20" class="percent"></td>
                  <td><input type="radio" name="Others_Unorganised" value="40" class="percent"></td>
                  <td><input type="radio" name="Others_Unorganised" value="60" class="percent"></td>
                  <td><input type="radio" name="Others_Unorganised" value="80" class="percent"></td>
                  <td><input type="radio" name="Others_Unorganised" value="100" class="percent"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
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
    const scriptURL = 'https://script.google.com/macros/s/AKfycbx18pbpszswuA-WvrwaZZy8-GWHTU1v_1zsZi-BHmopMYGrLuP3_E7lPQq3RcVSeHEU/exec';

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

    // Validate category channel percentages (must be exactly 100%)
    function validateCategoryPercentages(categoryDiv) {
      const inputs = categoryDiv.querySelectorAll('.percent:checked');
      let sum = 0;
      inputs.forEach(input => {
        sum += parseInt(input.value) || 0;
      });
      const errorMessage = categoryDiv.querySelector('.error-message');
      if (sum !== 100) {
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
        alert('Please ensure wardrobe percentages sum to 100% and channel percentages for each category sum to exactly 100%.');
      }
    });
  </script>
</body>
</html>
