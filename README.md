<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Style Insights | Fashion Survey</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Montserrat', sans-serif;
      background-color: #faf9f7;
    }
    .fashion-header {
      font-family: 'Playfair Display', serif;
    }
    .form-container {
      max-width: 900px;
      background: white;
      border-radius: 8px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
      border: 1px solid #f0e9e5;
    }
    .input-field, .select-field {
      transition: all 0.3s ease;
      border: 1px solid #e5e5e5;
      background-color: #fcfcfc;
    }
    .input-field:focus, .select-field:focus {
      border-color: #d4a373;
      box-shadow: 0 0 0 3px rgba(212, 163, 115, 0.1);
      background-color: white;
    }
    .section-title {
      border-bottom: 2px solid #f8f1e9;
      color: #333;
      letter-spacing: 0.5px;
    }
    .error-message {
      animation: fadeIn 0.3s ease-in;
      background-color: #fff0f0;
      border-left: 3px solid #e57373;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    th, td {
      text-align: center;
      padding: 12px;
      border: 1px solid #f0e9e5;
    }
    th {
      background-color: #f9f5f0;
      font-weight: 600;
      color: #5a4a42;
    }
    td:first-child {
      text-align: left;
      font-weight: 500;
      color: #5a4a42;
    }
    .channel-select {
      display: none;
    }
    .radio-input:checked {
      accent-color: #d4a373;
    }
    .submit-btn {
      background-color: #d4a373;
      transition: all 0.3s ease;
      letter-spacing: 0.5px;
    }
    .submit-btn:hover {
      background-color: #c08a5e;
      transform: translateY(-2px);
    }
    .category-tag {
      display: inline-block;
      background-color: #f8f1e9;
      color: #5a4a42;
      padding: 4px 12px;
      border-radius: 20px;
      font-size: 0.8rem;
      margin-right: 8px;
      margin-bottom: 8px;
    }
    .wardrobe-input-container {
      position: relative;
    }
    .wardrobe-input-container::after {
      content: '%';
      position: absolute;
      right: 15px;
      top: 50%;
      transform: translateY(-50%);
      color: #999;
      pointer-events: none;
    }
    @media (max-width: 640px) {
      .channel-table {
        display: none;
      }
      .channel-select {
        display: block;
      }
      .channel-select > div {
        margin-bottom: 1.5rem;
      }
      .channel-select label {
        display: block;
        font-weight: 500;
        color: #5a4a42;
        margin-bottom: 0.5rem;
        font-size: 0.9rem;
      }
      .channel-select select {
        width: 100%;
        padding: 0.75rem;
        border: 1px solid #e5e5e5;
        border-radius: 6px;
        background-color: #fcfcfc;
        font-size: 0.875rem;
        color: #333;
        appearance: none;
        background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3e%3cpolyline points='6 9 12 15 18 9'%3e%3c/polyline%3e%3c/svg%3e");
        background-repeat: no-repeat;
        background-position: right 0.75rem center;
        background-size: 1rem;
      }
      .channel-select select:focus {
        border-color: #d4a373;
        box-shadow: 0 0 0 3px rgba(212, 163, 115, 0.1);
        outline: none;
      }
    }
    @media (min-width: 641px) {
      .channel-table {
        display: block;
      }
    }
    .error-message, .wardrobe-error {
      font-size: 0.9rem;
      padding: 0.75rem;
      background-color: #fff0f0;
      border-radius: 0.375rem;
      border-left: 3px solid #e57373;
      margin-top: 0.5rem;
    }
    .brand-input {
      background-color: white;
      border: 1px solid #e5e5e5;
      transition: all 0.3s ease;
    }
    .brand-input:focus {
      border-color: #d4a373;
      box-shadow: 0 0 0 3px rgba(212, 163, 115, 0.1);
    }
    .fashion-banner {
      background: linear-gradient(135deg, #f8f1e9 0%, #f0e9e5 100%);
      border-radius: 8px;
      padding: 1.5rem;
      margin-bottom: 2rem;
    }
    .wardrobe-percent {
      padding-right: 30px !important;
    }
  </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 md:p-8">
  <div class="form-container mx-auto p-6 md:p-10 w-full">
    <div class="text-center mb-8">
      <h1 class="fashion-header text-3xl md:text-4xl font-bold text-gray-800 mb-2">Style Insights</h1>
      <p class="text-lg text-gray-600">Share your fashion preferences and help shape the future of style</p>
    </div>

    <div class="fashion-banner">
      <h2 class="fashion-header text-2xl font-semibold text-gray-800 mb-2">Wardrobe Survey</h2>
      <p class="text-gray-600">Your responses will help us understand fashion trends and preferences. All fields marked with * are required, and your information will remain confidential.</p>
    </div>

    <form id="surveyForm" class="space-y-8">
      <!-- Personal Information Section -->
      <div class="mb-8">
        <h2 class="fashion-header text-xl font-semibold text-gray-800 mb-4 section-title pb-2">Your Profile</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Name *</label>
            <input type="text" name="Name" class="input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Email *</label>
            <input type="text" name="Email" class="input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Age *</label>
            <input type="number" name="Age" min="1" max="120" class="input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Gender *</label>
            <select name="Gender" class="select-field w-full p-3 border rounded-lg focus:outline-none" required>
              <option value="">Select gender</option>
              <option value="Male">Male</option>
              <option value="Female">Female</option>
              <option value="Non-binary">Non-binary</option>
              <option value="Prefer not to say">Prefer not to say</option>
            </select>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">City *</label>
            <input type="text" name="City" class="input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
        </div>
      </div>

      <!-- Wardrobe Composition Section -->
      <div class="mb-8">
        <h2 class="fashion-header text-xl font-semibold text-gray-800 mb-4 section-title pb-2">Your Wardrobe Composition</h2>
        <p class="text-sm font-medium text-gray-600 mb-4">Estimate the percentage of your wardrobe for each category (total must sum to 100%): *</p>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div class="wardrobe-input-container">
            <label class="block text-sm font-medium text-gray-700 mb-1">Going out/Partywear (%) <span class="text-xs text-gray-500 block mt-1">Special occasion statement pieces</span></label>
            <input type="number" name="Wardrobe_Going_out" min="0" max="100" value="0" class="wardrobe-percent input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div class="wardrobe-input-container">
            <label class="block text-sm font-medium text-gray-700 mb-1">Casual Wear (%) <span class="text-xs text-gray-500 block mt-1">Everyday informal wear</span></label>
            <input type="number" name="Wardrobe_Casual" min="0" max="100" value="0" class="wardrobe-percent input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div class="wardrobe-input-container">
            <label class="block text-sm font-medium text-gray-700 mb-1">Formals/Semi-formals (%) <span class="text-xs text-gray-500 block mt-1">Professional or business attire</span></label>
            <input type="number" name="Wardrobe_Formals" min="0" max="100" value="0" class="wardrobe-percent input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div class="wardrobe-input-container">
            <label class="block text-sm font-medium text-gray-700 mb-1">Ethnic/Indo-western (%) <span class="text-xs text-gray-500 block mt-1">Traditional or fusion cultural wear</span></label>
            <input type="number" name="Wardrobe_Ethnic" min="0" max="100" value="0" class="wardrobe-percent input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
          <div class="wardrobe-input-container md:col-span-2">
            <label class="block text-sm font-medium text-gray-700 mb-1">Others (incl. Nightwear) (%) <span class="text-xs text-gray-500 block mt-1">Nightwear, gym wear, or specialty items</span></label>
            <input type="number" name="Wardrobe_Others" min="0" max="100" value="0" class="wardrobe-percent input-field w-full p-3 border rounded-lg focus:outline-none" required>
          </div>
        </div>
        <p class="text-red-500 text-sm mt-2 hidden wardrobe-error">Percentages must sum to 100%.</p>
      </div>

      <!-- Category Sections (Going out/Partywear) -->
      <div class="category mb-10 p-6 bg-white rounded-lg border border-gray-100 shadow-sm">
        <div class="flex items-center mb-4">
          <h2 class="fashion-header text-xl font-semibold text-gray-800">Going out/Partywear</h2>
          <span class="category-tag ml-2">Special Occasion</span>
        </div>
        <p class="text-sm text-gray-600 mb-6">Clothing designed for special occasions like parties, functions, or fancy dinners, where you wear statement pieces to stand out (e.g., cocktail dresses, tuxedos, sequined outfits).</p>
        
        <div class="mb-8">
          <p class="text-sm font-medium text-gray-600 mb-4">Where do you purchase these items? (Total must be 100%) *</p>
          <div class="channel-table overflow-x-auto">
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
                  <td><input type="radio" name="Going_out_Platforms" value="0" class="percent radio-input" id="going_out_platforms_0" required checked></td>
                  <td><input type="radio" name="Going_out_Platforms" value="20" class="percent radio-input" id="going_out_platforms_20"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="40" class="percent radio-input" id="going_out_platforms_40"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="60" class="percent radio-input" id="going_out_platforms_60"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="80" class="percent radio-input" id="going_out_platforms_80"></td>
                  <td><input type="radio" name="Going_out_Platforms" value="100" class="percent radio-input" id="going_out_platforms_100"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="0" class="percent radio-input" id="going_out_brand_websites_0" required checked></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="20" class="percent radio-input" id="going_out_brand_websites_20"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="40" class="percent radio-input" id="going_out_brand_websites_40"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="60" class="percent radio-input" id="going_out_brand_websites_60"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="80" class="percent radio-input" id="going_out_brand_websites_80"></td>
                  <td><input type="radio" name="Going_out_Brand_Websites" value="100" class="percent radio-input" id="going_out_brand_websites_100"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Going_out_D2C" value="0" class="percent radio-input" id="going_out_d2c_0" required checked></td>
                  <td><input type="radio" name="Going_out_D2C" value="20" class="percent radio-input" id="going_out_d2c_20"></td>
                  <td><input type="radio" name="Going_out_D2C" value="40" class="percent radio-input" id="going_out_d2c_40"></td>
                  <td><input type="radio" name="Going_out_D2C" value="60" class="percent radio-input" id="going_out_d2c_60"></td>
                  <td><input type="radio" name="Going_out_D2C" value="80" class="percent radio-input" id="going_out_d2c_80"></td>
                  <td><input type="radio" name="Going_out_D2C" value="100" class="percent radio-input" id="going_out_d2c_100"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Going_out_Offline" value="0" class="percent radio-input" id="going_out_offline_0" required checked></td>
                  <td><input type="radio" name="Going_out_Offline" value="20" class="percent radio-input" id="going_out_offline_20"></td>
                  <td><input type="radio" name="Going_out_Offline" value="40" class="percent radio-input" id="going_out_offline_40"></td>
                  <td><input type="radio" name="Going_out_Offline" value="60" class="percent radio-input" id="going_out_offline_60"></td>
                  <td><input type="radio" name="Going_out_Offline" value="80" class="percent radio-input" id="going_out_offline_80"></td>
                  <td><input type="radio" name="Going_out_Offline" value="100" class="percent radio-input" id="going_out_offline_100"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Going_out_Unorganised" value="0" class="percent radio-input" id="going_out_unorganised_0" required checked></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="20" class="percent radio-input" id="going_out_unorganised_20"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="40" class="percent radio-input" id="going_out_unorganised_40"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="60" class="percent radio-input" id="going_out_unorganised_60"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="80" class="percent radio-input" id="going_out_unorganised_80"></td>
                  <td><input type="radio" name="Going_out_Unorganised" value="100" class="percent radio-input" id="going_out_unorganised_100"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="channel-select">
            <div>
              <label>Platforms like Myntra/Ajio</label>
              <select name="Going_out_Platforms" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Brand Websites</label>
              <select name="Going_out_Brand_Websites" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>D2C/Social Media</label>
              <select name="Going_out_D2C" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Offline (Malls and Stores)</label>
              <select name="Going_out_Offline" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Unorganised/Thrifted</label>
              <select name="Going_out_Unorganised" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">Your favorite brands for Going out/Partywear:</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" name="Going_out_Brand1" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="brand-input w-full p-3 border rounded-lg focus:outline-none md:col-span-2" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Casual Wear Section -->
      <div class="category mb-10 p-6 bg-white rounded-lg border border-gray-100 shadow-sm">
        <div class="flex items-center mb-4">
          <h2 class="fashion-header text-xl font-semibold text-gray-800">Casual Wear</h2>
          <span class="category-tag ml-2">Everyday Style</span>
        </div>
        <p class="text-sm text-gray-600 mb-6">Everyday clothing for informal settings like travel, casual brunches, meeting friends, or lounging at home, prioritizing comfort and simplicity (e.g., t-shirts, jeans, sneakers, loungewear).</p>
        
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="channel-table overflow-x-auto">
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
                  <td><input type="radio" name="Casual_Platforms" value="0" class="percent radio-input" id="casual_platforms_0" required checked></td>
                  <td><input type="radio" name="Casual_Platforms" value="20" class="percent radio-input" id="casual_platforms_20"></td>
                  <td><input type="radio" name="Casual_Platforms" value="40" class="percent radio-input" id="casual_platforms_40"></td>
                  <td><input type="radio" name="Casual_Platforms" value="60" class="percent radio-input" id="casual_platforms_60"></td>
                  <td><input type="radio" name="Casual_Platforms" value="80" class="percent radio-input" id="casual_platforms_80"></td>
                  <td><input type="radio" name="Casual_Platforms" value="100" class="percent radio-input" id="casual_platforms_100"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="0" class="percent radio-input" id="casual_brand_websites_0" required checked></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="20" class="percent radio-input" id="casual_brand_websites_20"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="40" class="percent radio-input" id="casual_brand_websites_40"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="60" class="percent radio-input" id="casual_brand_websites_60"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="80" class="percent radio-input" id="casual_brand_websites_80"></td>
                  <td><input type="radio" name="Casual_Brand_Websites" value="100" class="percent radio-input" id="casual_brand_websites_100"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Casual_D2C" value="0" class="percent radio-input" id="casual_d2c_0" required checked></td>
                  <td><input type="radio" name="Casual_D2C" value="20" class="percent radio-input" id="casual_d2c_20"></td>
                  <td><input type="radio" name="Casual_D2C" value="40" class="percent radio-input" id="casual_d2c_40"></td>
                  <td><input type="radio" name="Casual_D2C" value="60" class="percent radio-input" id="casual_d2c_60"></td>
                  <td><input type="radio" name="Casual_D2C" value="80" class="percent radio-input" id="casual_d2c_80"></td>
                  <td><input type="radio" name="Casual_D2C" value="100" class="percent radio-input" id="casual_d2c_100"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Casual_Offline" value="0" class="percent radio-input" id="casual_offline_0" required checked></td>
                  <td><input type="radio" name="Casual_Offline" value="20" class="percent radio-input" id="casual_offline_20"></td>
                  <td><input type="radio" name="Casual_Offline" value="40" class="percent radio-input" id="casual_offline_40"></td>
                  <td><input type="radio" name="Casual_Offline" value="60" class="percent radio-input" id="casual_offline_60"></td>
                  <td><input type="radio" name="Casual_Offline" value="80" class="percent radio-input" id="casual_offline_80"></td>
                  <td><input type="radio" name="Casual_Offline" value="100" class="percent radio-input" id="casual_offline_100"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Casual_Unorganised" value="0" class="percent radio-input" id="casual_unorganised_0" required checked></td>
                  <td><input type="radio" name="Casual_Unorganised" value="20" class="percent radio-input" id="casual_unorganised_20"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="40" class="percent radio-input" id="casual_unorganised_40"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="60" class="percent radio-input" id="casual_unorganised_60"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="80" class="percent radio-input" id="casual_unorganised_80"></td>
                  <td><input type="radio" name="Casual_Unorganised" value="100" class="percent radio-input" id="casual_unorganised_100"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="channel-select">
            <div>
              <label>Platforms like Myntra/Ajio</label>
              <select name="Casual_Platforms" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Brand Websites</label>
              <select name="Casual_Brand_Websites" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>D2C/Social Media</label>
              <select name="Casual_D2C" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Offline (Malls and Stores)</label>
              <select name="Casual_Offline" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Unorganised/Thrifted</label>
              <select name="Casual_Unorganised" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">Your favorite brands for Going out/Partywear:</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" name="Going_out_Brand1" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="brand-input w-full p-3 border rounded-lg focus:outline-none md:col-span-2" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Formals/Semi-formals Section -->
      <div class="category mb-10 p-6 bg-white rounded-lg border border-gray-100 shadow-sm">
        <div class="flex items-center mb-4">
          <h2 class="fashion-header text-xl font-semibold text-gray-800">Formals/Semi-formals</h2>
          <span class="category-tag ml-2">Professional</span>
        </div>
        <p class="text-sm text-gray-600 mb-6">Professional or business-appropriate clothing for workplaces, meetings, or semi-formal events, typically structured and polished (e.g., suits, blazers, dress shirts).</p>
        
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="channel-table overflow-x-auto">
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
                  <td><input type="radio" name="Formals_Platforms" value="0" class="percent radio-input" id="formals_platforms_0" required checked></td>
                  <td><input type="radio" name="Formals_Platforms" value="20" class="percent radio-input" id="formals_platforms_20"></td>
                  <td><input type="radio" name="Formals_Platforms" value="40" class="percent radio-input" id="formals_platforms_40"></td>
                  <td><input type="radio" name="Formals_Platforms" value="60" class="percent radio-input" id="formals_platforms_60"></td>
                  <td><input type="radio" name="Formals_Platforms" value="80" class="percent radio-input" id="formals_platforms_80"></td>
                  <td><input type="radio" name="Formals_Platforms" value="100" class="percent radio-input" id="formals_platforms_100"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="0" class="percent radio-input" id="formals_brand_websites_0" required checked></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="20" class="percent radio-input" id="formals_brand_websites_20"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="40" class="percent radio-input" id="formals_brand_websites_40"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="60" class="percent radio-input" id="formals_brand_websites_60"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="80" class="percent radio-input" id="formals_brand_websites_80"></td>
                  <td><input type="radio" name="Formals_Brand_Websites" value="100" class="percent radio-input" id="formals_brand_websites_100"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Formals_D2C" value="0" class="percent radio-input" id="formals_d2c_0" required checked></td>
                  <td><input type="radio" name="Formals_D2C" value="20" class="percent radio-input" id="formals_d2c_20"></td>
                  <td><input type="radio" name="Formals_D2C" value="40" class="percent radio-input" id="formals_d2c_40"></td>
                  <td><input type="radio" name="Formals_D2C" value="60" class="percent radio-input" id="formals_d2c_60"></td>
                  <td><input type="radio" name="Formals_D2C" value="80" class="percent radio-input" id="formals_d2c_80"></td>
                  <td><input type="radio" name="Formals_D2C" value="100" class="percent radio-input" id="formals_d2c_100"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Formals_Offline" value="0" class="percent radio-input" id="formals_offline_0" required checked></td>
                  <td><input type="radio" name="Formals_Offline" value="20" class="percent radio-input" id="formals_offline_20"></td>
                  <td><input type="radio" name="Formals_Offline" value="40" class="percent radio-input" id="formals_offline_40"></td>
                  <td><input type="radio" name="Formals_Offline" value="60" class="percent radio-input" id="formals_offline_60"></td>
                  <td><input type="radio" name="Formals_Offline" value="80" class="percent radio-input" id="formals_offline_80"></td>
                  <td><input type="radio" name="Formals_Offline" value="100" class="percent radio-input" id="formals_offline_100"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Formals_Unorganised" value="0" class="percent radio-input" id="formals_unorganised_0" required checked></td>
                  <td><input type="radio" name="Formals_Unorganised" value="20" class="percent radio-input" id="formals_unorganised_20"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="40" class="percent radio-input" id="formals_unorganised_40"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="60" class="percent radio-input" id="formals_unorganised_60"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="80" class="percent radio-input" id="formals_unorganised_80"></td>
                  <td><input type="radio" name="Formals_Unorganised" value="100" class="percent radio-input" id="formals_unorganised_100"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="channel-select">
            <div>
              <label>Platforms like Myntra/Ajio</label>
              <select name="Formals_Platforms" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Brand Websites</label>
              <select name="Formals_Brand_Websites" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>D2C/Social Media</label>
              <select name="Formals_D2C" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Offline (Malls and Stores)</label>
              <select name="Formals_Offline" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Unorganised/Thrifted</label>
              <select name="Formals_Unorganised" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">Your favorite brands for Going out/Partywear:</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" name="Going_out_Brand1" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="brand-input w-full p-3 border rounded-lg focus:outline-none md:col-span-2" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Ethnic/Indo-western Section -->
      <div class="category mb-10 p-6 bg-white rounded-lg border border-gray-100 shadow-sm">
        <div class="flex items-center mb-4">
          <h2 class="fashion-header text-xl font-semibold text-gray-800">Ethnic/Indo-western</h2>
          <span class="category-tag ml-2">Cultural</span>
        </div>
        <p class="text-sm text-gray-600 mb-6">Traditional or fusion clothing reflecting cultural heritage or modern adaptations, worn for festivals, weddings, or cultural events (e.g., sarees, kurtas, lehengas, Indo-western dresses).</p>
        
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="channel-table overflow-x-auto">
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
                  <td><input type="radio" name="Ethnic_Platforms" value="0" class="percent radio-input" id="ethnic_platforms_0" required checked></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="20" class="percent radio-input" id="ethnic_platforms_20"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="40" class="percent radio-input" id="ethnic_platforms_40"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="60" class="percent radio-input" id="ethnic_platforms_60"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="80" class="percent radio-input" id="ethnic_platforms_80"></td>
                  <td><input type="radio" name="Ethnic_Platforms" value="100" class="percent radio-input" id="ethnic_platforms_100"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="0" class="percent radio-input" id="ethnic_brand_websites_0" required checked></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="20" class="percent radio-input" id="ethnic_brand_websites_20"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="40" class="percent radio-input" id="ethnic_brand_websites_40"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="60" class="percent radio-input" id="ethnic_brand_websites_60"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="80" class="percent radio-input" id="ethnic_brand_websites_80"></td>
                  <td><input type="radio" name="Ethnic_Brand_Websites" value="100" class="percent radio-input" id="ethnic_brand_websites_100"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Ethnic_D2C" value="0" class="percent radio-input" id="ethnic_d2c_0" required checked></td>
                  <td><input type="radio" name="Ethnic_D2C" value="20" class="percent radio-input" id="ethnic_d2c_20"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="40" class="percent radio-input" id="ethnic_d2c_40"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="60" class="percent radio-input" id="ethnic_d2c_60"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="80" class="percent radio-input" id="ethnic_d2c_80"></td>
                  <td><input type="radio" name="Ethnic_D2C" value="100" class="percent radio-input" id="ethnic_d2c_100"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Ethnic_Offline" value="0" class="percent radio-input" id="ethnic_offline_0" required checked></td>
                  <td><input type="radio" name="Ethnic_Offline" value="20" class="percent radio-input" id="ethnic_offline_20"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="40" class="percent radio-input" id="ethnic_offline_40"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="60" class="percent radio-input" id="ethnic_offline_60"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="80" class="percent radio-input" id="ethnic_offline_80"></td>
                  <td><input type="radio" name="Ethnic_Offline" value="100" class="percent radio-input" id="ethnic_offline_100"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="0" class="percent radio-input" id="ethnic_unorganised_0" required checked></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="20" class="percent radio-input" id="ethnic_unorganised_20"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="40" class="percent radio-input" id="ethnic_unorganised_40"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="60" class="percent radio-input" id="ethnic_unorganised_60"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="80" class="percent radio-input" id="ethnic_unorganised_80"></td>
                  <td><input type="radio" name="Ethnic_Unorganised" value="100" class="percent radio-input" id="ethnic_unorganised_100"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="channel-select">
            <div>
              <label>Platforms like Myntra/Ajio</label>
              <select name="Ethnic_Platforms" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Brand Websites</label>
              <select name="Ethnic_Brand_Websites" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>D2C/Social Media</label>
              <select name="Ethnic_D2C" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Offline (Malls and Stores)</label>
              <select name="Ethnic_Offline" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Unorganised/Thrifted</label>
              <select name="Ethnic_Unorganised" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">Your favorite brands for Going out/Partywear:</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" name="Going_out_Brand1" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="brand-input w-full p-3 border rounded-lg focus:outline-none md:col-span-2" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <!-- Others Section -->
      <div class="category mb-10 p-6 bg-white rounded-lg border border-gray-100 shadow-sm">
        <div class="flex items-center mb-4">
          <h2 class="fashion-header text-xl font-semibold text-gray-800">Others (incl. Nightwear)</h2>
          <span class="category-tag ml-2">Specialty</span>
        </div>
        <p class="text-sm text-gray-600 mb-6">Miscellaneous clothing not covered by other categories, including nightwear, gym wear, or other specialty items (e.g., pajamas, athletic wear, costumes).</p>
        
        <div class="mb-6">
          <p class="text-sm font-medium text-gray-600 mb-3">Purchase Channel Split (select a percentage for each channel; total must be exactly 100%). Round your estimates to the nearest option using: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%. Select one option per channel: *</p>
          <div class="channel-table overflow-x-auto">
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
                  <td><input type="radio" name="Others_Platforms" value="0" class="percent radio-input" id="others_platforms_0" required checked></td>
                  <td><input type="radio" name="Others_Platforms" value="20" class="percent radio-input" id="others_platforms_20"></td>
                  <td><input type="radio" name="Others_Platforms" value="40" class="percent radio-input" id="others_platforms_40"></td>
                  <td><input type="radio" name="Others_Platforms" value="60" class="percent radio-input" id="others_platforms_60"></td>
                  <td><input type="radio" name="Others_Platforms" value="80" class="percent radio-input" id="others_platforms_80"></td>
                  <td><input type="radio" name="Others_Platforms" value="100" class="percent radio-input" id="others_platforms_100"></td>
                </tr>
                <tr>
                  <td>Brand Websites</td>
                  <td><input type="radio" name="Others_Brand_Websites" value="0" class="percent radio-input" id="others_brand_websites_0" required checked></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="20" class="percent radio-input" id="others_brand_websites_20"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="40" class="percent radio-input" id="others_brand_websites_40"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="60" class="percent radio-input" id="others_brand_websites_60"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="80" class="percent radio-input" id="others_brand_websites_80"></td>
                  <td><input type="radio" name="Others_Brand_Websites" value="100" class="percent radio-input" id="others_brand_websites_100"></td>
                </tr>
                <tr>
                  <td>D2C/Social Media</td>
                  <td><input type="radio" name="Others_D2C" value="0" class="percent radio-input" id="others_d2c_0" required checked></td>
                  <td><input type="radio" name="Others_D2C" value="20" class="percent radio-input" id="others_d2c_20"></td>
                  <td><input type="radio" name="Others_D2C" value="40" class="percent radio-input" id="others_d2c_40"></td>
                  <td><input type="radio" name="Others_D2C" value="60" class="percent radio-input" id="others_d2c_60"></td>
                  <td><input type="radio" name="Others_D2C" value="80" class="percent radio-input" id="others_d2c_80"></td>
                  <td><input type="radio" name="Others_D2C" value="100" class="percent radio-input" id="others_d2c_100"></td>
                </tr>
                <tr>
                  <td>Offline (Malls and Stores)</td>
                  <td><input type="radio" name="Others_Offline" value="0" class="percent radio-input" id="others_offline_0" required checked></td>
                  <td><input type="radio" name="Others_Offline" value="20" class="percent radio-input" id="others_offline_20"></td>
                  <td><input type="radio" name="Others_Offline" value="40" class="percent radio-input" id="others_offline_40"></td>
                  <td><input type="radio" name="Others_Offline" value="60" class="percent radio-input" id="others_offline_60"></td>
                  <td><input type="radio" name="Others_Offline" value="80" class="percent radio-input" id="others_offline_80"></td>
                  <td><input type="radio" name="Others_Offline" value="100" class="percent radio-input" id="others_offline_100"></td>
                </tr>
                <tr>
                  <td>Unorganised/Thrifted</td>
                  <td><input type="radio" name="Others_Unorganised" value="0" class="percent radio-input" id="others_unorganised_0" required checked></td>
                  <td><input type="radio" name="Others_Unorganised" value="20" class="percent radio-input" id="others_unorganised_20"></td>
                  <td><input type="radio" name="Others_Unorganised" value="40" class="percent radio-input" id="others_unorganised_40"></td>
                  <td><input type="radio" name="Others_Unorganised" value="60" class="percent radio-input" id="others_unorganised_60"></td>
                  <td><input type="radio" name="Others_Unorganised" value="80" class="percent radio-input" id="others_unorganised_80"></td>
                  <td><input type="radio" name="Others_Unorganised" value="100" class="percent radio-input" id="others_unorganised_100"></td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="channel-select">
            <div>
              <label>Platforms like Myntra/Ajio</label>
              <select name="Others_Platforms" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Brand Websites</label>
              <select name="Others_Brand_Websites" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>D2C/Social Media</label>
              <select name="Others_D2C" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Offline (Malls and Stores)</label>
              <select name="Others_Offline" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
            <div>
              <label>Unorganised/Thrifted</label>
              <select name="Others_Unorganised" class="percent dropdown-input" required>
                <option value="0" selected>0%</option>
                <option value="20">20%</option>
                <option value="40">40%</option>
                <option value="60">60%</option>
                <option value="80">80%</option>
                <option value="100">100%</option>
              </select>
            </div>
          </div>
          <p class="text-red-500 text-sm mt-2 hidden error-message">The sum of channel percentages must be exactly 100%. Please adjust your selections.</p>
        </div>
        <div>
          <p class="text-sm font-medium text-gray-600 mb-3">Your favorite brands for Going out/Partywear:</p>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <input type="text" name="Going_out_Brand1" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 1">
            <input type="text" name="Going_out_Brand2" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 2">
            <input type="text" name="Going_out_Brand3" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 3">
            <input type="text" name="Going_out_Brand4" class="brand-input w-full p-3 border rounded-lg focus:outline-none" placeholder="Brand 4">
            <input type="text" name="Going_out_Brand5" class="brand-input w-full p-3 border rounded-lg focus:outline-none md:col-span-2" placeholder="Brand 5">
          </div>
        </div>
      </div>

      <div class="text-center mt-12">
        <button type="submit" id="submitBtn" class="submit-btn text-white px-10 py-4 rounded-lg text-lg font-medium">Submit Your Style Insights</button>
        <p class="text-xs text-gray-500 mt-3">Your responses will help shape the future of fashion</p>
      </div>
    </form>
  </div>

  <script>
    const form = document.getElementById('surveyForm');
    const scriptURL = 'https://script.google.com/macros/s/AKfycbx18pbpszswuA-WvrwaZZy8-GWHTU1v_1zsZi-BHmopMYGrLuP3_E7lPQq3RcVSeHEU/exec';
    const MOBILE_BREAKPOINT = 640;

    // Synchronize radio buttons and dropdowns
    function syncInputs(source, targetClass) {
      const name = source.name;
      const value = source.value || "0";
      console.log(`Syncing ${source.tagName} ${name}: Source Value = ${value}`);

      const targets = document.querySelectorAll(`.${targetClass}[name="${name}"]`);
      targets.forEach(target => {
        if (target.tagName === 'INPUT' && target.type === 'radio') {
          const isChecked = target.value === value;
          target.checked = isChecked;
          console.log(`Set radio ${target.id} (value=${target.value}) checked=${isChecked}`);
        } else if (target.tagName === 'SELECT') {
          target.value = value;
          console.log(`Set dropdown ${target.name} to value=${value}`);
        }
      });
    }

    // Initialize dropdowns and radio buttons on page load
    function initializeInputs() {
      console.log("Initializing inputs on page load...");
      const radioInputs = document.querySelectorAll('.radio-input');
      const dropdownInputs = document.querySelectorAll('.dropdown-input');

      // Ensure all radio buttons have a default selection
      const radioGroups = new Set();
      radioInputs.forEach(radio => {
        radioGroups.add(radio.name);
      });
      radioGroups.forEach(name => {
        const radios = document.querySelectorAll(`.radio-input[name="${name}"]`);
        const checkedRadio = Array.from(radios).find(radio => radio.checked);
        if (!checkedRadio) {
          const firstRadio = radios[0];
          firstRadio.checked = true;
          console.log(`No radio selected for ${name}, defaulting to ${firstRadio.value}`);
          syncInputs(firstRadio, 'dropdown-input');
        } else {
          syncInputs(checkedRadio, 'dropdown-input');
        }
      });

      // Ensure all dropdowns have a default selection
      dropdownInputs.forEach(dropdown => {
        if (!dropdown.value) {
          dropdown.value = "0";
          console.log(`No value selected for dropdown ${dropdown.name}, defaulting to 0`);
          syncInputs(dropdown, 'radio-input');
        }
      });

      console.log("Initialization complete.");
    }

    // Add event listeners to sync inputs
    document.querySelectorAll('.radio-input').forEach(radio => {
      radio.addEventListener('change', () => {
        if (radio.checked) {
          syncInputs(radio, 'dropdown-input');
        }
      });
    });

    document.querySelectorAll('.dropdown-input').forEach(dropdown => {
      dropdown.addEventListener('change', () => {
        syncInputs(dropdown, 'radio-input');
      });
    });

    // Validate wardrobe percentages (must sum to 100%)
    function validateWardrobe() {
      const inputs = document.querySelectorAll('.wardrobe-percent');
      let sum = 0;

      inputs.forEach(input => {
        input.dispatchEvent(new Event('input', { bubbles: true }));
        const rawValue = input.value;
        const parsedValue = parseInt(rawValue) || 0;
        console.log(`Wardrobe Input ${input.name}: Raw Value = ${rawValue}, Parsed Value = ${parsedValue}`);
        sum += parsedValue;
      });

      console.log(`Wardrobe Sum: ${sum}, Valid: ${sum === 100}`);
      const errorMessage = document.querySelector('.wardrobe-error');
      errorMessage.classList.toggle('hidden', sum === 100);
      return sum === 100;
    }

    // Validate category channel percentages (must be exactly 100%)
    function validateCategoryPercentages(categoryDiv) {
      const isMobile = window.innerWidth <= MOBILE_BREAKPOINT;
      const selector = isMobile ? '.dropdown-input' : '.radio-input';
      const inputs = categoryDiv.querySelectorAll(selector);
      let sum = 0;

      inputs.forEach(input => {
        let value = 0;
        if (input.tagName === 'INPUT' && input.checked) {
          value = parseInt(input.value) || 0;
        } else if (input.tagName === 'SELECT') {
          value = parseInt(input.value) || 0;
        }
        console.log(`Input: ${input.name} Value: ${value}`);
        sum += value;
      });

      console.log(`Category Sum: ${sum}`);
      const errorMessage = categoryDiv.querySelector('.error-message');
      errorMessage.classList.toggle('hidden', sum === 100);
      return sum === 100;
    }

    // Validate entire form
    function validateForm() {
      const wardrobeValid = validateWardrobe();
      const categories = document.querySelectorAll('.category');
      const categoriesValid = Array.from(categories).every(category => validateCategoryPercentages(category));
      const isValid = wardrobeValid && categoriesValid;
      console.log(`Form Validation Result: ${isValid}`);
      return isValid;
    }

    // Handle form submission
    form.addEventListener('submit', e => {
      e.preventDefault();
      console.log('Submit button clicked');
      if (validateForm()) {
        console.log('Validation passed, submitting form');
        fetch(scriptURL, {
          method: 'POST',
          body: new FormData(form),
          redirect: 'follow'
        })
        .then(response => {
          console.log('Fetch Response Status:', response.status);
          console.log('Fetch Response Headers:', response.headers);
          if (!response.ok) {
            throw new Error(`HTTP error! Status: ${response.status}`);
          }
          return response.text();
        })
        .then(data => {
          console.log('Fetch Response Body:', data);
          alert('Thank you! Your survey has been submitted successfully.');
          form.reset();
          initializeInputs();
        })
        .catch(error => {
          console.error('Error submitting form:', error);
          alert('There was an error submitting your survey. Please try again later.');
        });
      } else {
        console.log('Form validation failed');
        alert('Please correct the errors in the form before submitting.');
      }
    });

    // Re-validate and sync on window resize to handle view changes
    let lastWidth = window.innerWidth;
    window.addEventListener('resize', () => {
      const currentWidth = window.innerWidth;
      const viewChanged = (lastWidth <= MOBILE_BREAKPOINT && currentWidth > MOBILE_BREAKPOINT) || 
                          (lastWidth > MOBILE_BREAKPOINT && currentWidth <= MOBILE_BREAKPOINT);
      if (viewChanged) {
        console.log(`View changed: ${lastWidth > MOBILE_BREAKPOINT ? 'Desktop' : 'Mobile'} to ${currentWidth > MOBILE_BREAKPOINT ? 'Desktop' : 'Mobile'}`);
        const isMobile = currentWidth <= MOBILE_BREAKPOINT;
        const sourceClass = isMobile ? 'dropdown-input' : 'radio-input';
        const targetClass = isMobile ? 'radio-input' : 'dropdown-input';
        const sources = document.querySelectorAll(`.${sourceClass}`);
        sources.forEach(source => {
          if (source.tagName === 'INPUT' && source.checked) {
            syncInputs(source, targetClass);
          } else if (source.tagName === 'SELECT') {
            syncInputs(source, targetClass);
          }
        });
        validateForm();
      }
      lastWidth = currentWidth;
    });

    // Run initialization on page load
    document.addEventListener('DOMContentLoaded', initializeInputs);
  </script>
</body>
</html>
