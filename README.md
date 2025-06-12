
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Professional Fashion Survey - Wardrobe Insights</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #4b5563;
      --primary-light: #6b7280;
      --primary-dark: #374151;
      --secondary: #a8a29e;
      --accent: #d6d3d1;
      --light-bg: #f5f5f4;
      --card-bg: #ffffff;
      --border: #e7e5e4;
      --success: #10b981;
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--light-bg);
      color: #292524;
      line-height: 1.6;
      min-height: 100vh;
      padding: 20px;
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(231, 229, 228, 0.3) 0%, rgba(255, 255, 255, 0) 40%),
        radial-gradient(circle at 90% 80%, rgba(231, 229, 228, 0.3) 0%, rgba(255, 255, 255, 0) 40%);
    }
    
    .container {
      max-width: 1000px;
      margin: 0 auto;
    }
    
    .form-container {
      background: var(--card-bg);
      border-radius: 12px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
      border: 1px solid var(--border);
      padding: 2.5rem;
      position: relative;
      margin: 2rem auto;
      overflow: hidden;
      transition: all 0.3s ease;
    }
    
    .form-container:hover {
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.08);
    }
    
    .form-container::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 6px;
      background: linear-gradient(90deg, var(--primary), var(--primary-light));
      opacity: 0.9;
    }
    
    h1 {
      font-family: 'Playfair Display', serif;
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--primary-dark);
      text-align: center;
      margin-bottom: 1.25rem;
      position: relative;
      padding-bottom: 1rem;
    }
    
    h1::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 100px;
      height: 4px;
      background: linear-gradient(to right, var(--primary), var(--primary-light));
      border-radius: 2px;
    }
    
    h2 {
      font-family: 'Inter', sans-serif;
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--primary-dark);
      position: relative;
      margin-bottom: 1.5rem;
      padding-bottom: 0.75rem;
    }
    
    h2::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 60px;
      height: 3px;
      background: linear-gradient(to right, var(--primary), var(--primary-light));
      border-radius: 2px;
    }
    
    .section-card {
      background: var(--card-bg);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.75rem;
      margin-bottom: 2rem;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    
    .section-card:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 25px rgba(0, 0, 0, 0.05);
    }
    
    .input-field, .select-field, select {
      background-color: #fafafa;
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 0.85rem 1.25rem;
      transition: all 0.3s ease;
      font-size: 0.95rem;
      color: #292524;
      width: 100%;
      box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.02);
    }
    
    .input-field:focus, .select-field:focus, select:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(75, 85, 99, 0.1);
      outline: none;
    }
    
    .input-field:hover, .select-field:hover, select:hover {
      border-color: var(--accent);
    }
    
    .error-message, .wardrobe-error {
      background-color: #fef3c7;
      color: #92400e;
      border-radius: 8px;
      padding: 0.85rem 1.25rem;
      font-size: 0.9rem;
      animation: fadeIn 0.3s ease-in;
      border-left: 4px solid #f59e0b;
      margin-top: 0.5rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .wardrobe-error {
      margin-top: 1rem;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-5px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    th, td {
      text-align: center;
      padding: 14px 12px;
      border: 1px solid var(--border);
    }
    
    th {
      background: #f5f5f4;
      font-weight: 600;
      color: var(--primary-dark);
    }
    
    td:first-child {
      text-align: left;
      font-weight: 500;
      color: #44403c;
    }
    
    .radio-input, .dropdown-input {
      accent-color: var(--primary);
    }
    
    .channel-select {
      display: none;
    }
    
    .channel-table {
      border-radius: 8px;
      overflow: hidden;
      background: #fff;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.02);
    }
    
    .channel-table th, .channel-table td {
      transition: background-color 0.2s;
    }
    
    .channel-table tr:hover td {
      background-color: #fafaf9;
    }
    
    @media (max-width: 640px) {
      .channel-table {
        display: none;
      }
      .channel-select {
        display: block;
      }
      .channel-select > div {
        margin-bottom: 1.25rem;
      }
      .channel-select label {
        display: block;
        font-weight: 500;
        color: var(--primary-dark);
        margin-bottom: 0.5rem;
        font-size: 0.95rem;
      }
      .channel-select select {
        width: 100%;
        padding: 0.85rem;
        border: 1px solid var(--border);
        border-radius: 8px;
        background-color: #fafafa;
        font-size: 0.95rem;
        color: #292524;
      }
      .channel-select select:focus {
        border-color: var(--primary);
        box-shadow: 0 0 0 3px rgba(75, 85, 99, 0.1);
        outline: none;
      }
      .form-container {
        padding: 1.75rem;
      }
      h1 {
        font-size: 2rem;
      }
      h2 {
        font-size: 1.3rem;
      }
    }
    
    @media (min-width: 641px) {
      .channel-table {
        display: block;
      }
    }
    
    button {
      background: linear-gradient(45deg, var(--primary), var(--primary-light));
      border: none;
      padding: 1rem 3rem;
      border-radius: 50px;
      font-family: 'Inter', sans-serif;
      font-weight: 600;
      font-size: 1.05rem;
      color: #fff;
      transition: all 0.3s ease;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      box-shadow: 0 4px 15px rgba(75, 85, 99, 0.2);
      letter-spacing: 0.5px;
    }
    
    button:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(75, 85, 99, 0.3);
      background: linear-gradient(45deg, var(--primary-dark), var(--primary));
    }
    
    button:active {
      transform: translateY(0);
    }
    
    button::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -60%;
      width: 40px;
      height: 200%;
      background: rgba(255, 255, 255, 0.2);
      transform: rotate(30deg);
      transition: all 0.6s;
    }
    
    button:hover::after {
      left: 120%;
    }
    
    label {
      color: #44403c;
      font-weight: 500;
      font-size: 0.95rem;
      margin-bottom: 0.5rem;
      display: block;
    }
    
    p {
      color: #57534e;
      font-size: 0.95rem;
      line-height: 1.7;
    }
    
    input::placeholder {
      color: #a8a29e;
      font-style: normal;
    }
    
    .form-description {
      text-align: center;
      max-width: 700px;
      margin: 0 auto 2rem;
      color: #57534e;
      font-size: 1.05rem;
    }
    
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
    }
    
    .brand-inputs {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1rem;
    }
    
    .progress-bar {
      height: 6px;
      background: #e7e5e4;
      border-radius: 3px;
      margin: 1.5rem 0;
      overflow: hidden;
    }
    
    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--primary), var(--primary-light));
      border-radius: 3px;
      width: 0%;
      transition: width 0.5s ease;
    }
    
    .section-title-icon {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 36px;
      height: 36px;
      background: linear-gradient(45deg, var(--primary), var(--primary-light));
      color: white;
      border-radius: 50%;
      margin-right: 12px;
      font-size: 16px;
    }
    
    .input-group {
      position: relative;
    }
    
    .input-group i {
      position: absolute;
      right: 15px;
      top: 50%;
      transform: translateY(-50%);
      color: var(--primary);
      opacity: 0.7;
    }
    
    .percent-value {
      display: inline-block;
      min-width: 40px;
      text-align: center;
      font-weight: 600;
      color: var(--primary);
    }
    
    .form-footer {
      text-align: center;
      padding-top: 1.5rem;
      color: #78716c;
      font-size: 0.9rem;
      border-top: 1px solid var(--border);
      margin-top: 1rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="form-container">
      <h1>Fashion Survey - Wardrobe Insights</h1>
      <p class="form-description">Share your style preferences and shopping habits. All fields marked with * are required, and your responses are confidential.</p>
      
      <div class="progress-bar">
        <div class="progress-fill" id="progressFill"></div>
      </div>
      
      <form id="surveyForm" class="space-y-10">
        <div class="section-card">
          <h2><span class="section-title-icon"><i class="fas fa-user"></i></span>Personal Information</h2>
          <div class="grid grid-2 gap-6">
            <div class="input-group">
              <label>Name *</label>
              <input type="text" name="Name" class="input-field w-full" required>
              <i class="fas fa-user"></i>
            </div>
            <div class="input-group">
              <label>Email *</label>
              <input type="email" name="Email" class="input-field w-full" required>
              <i class="fas fa-envelope"></i>
            </div>
            <div class="input-group">
              <label>Age *</label>
              <select name="Age" class="select-field w-full" required>
                <option value="">Select age range</option>
                <option value="18-25">18–25</option>
                <option value="26-30">26–30</option>
                <option value="31-35">31–35</option>
                <option value="36-40">36–40</option>
              </select>
              <i class="fas fa-caret-down"></i>
            </div>
            <div class="input-group">
              <label>City *</label>
              <input type="text" name="City" class="input-field w-full" required>
              <i class="fas fa-city"></i>
            </div>
          </div>
        </div>

        <div class="section-card">
          <h2><span class="section-title-icon"><i class="fas fa-tshirt"></i></span>Wardrobe Composition</h2>
          <p>Estimate the percentage of your wardrobe for each category (total must sum to 100%): *</p>
          <div class="space-y-4 mt-5">
            <div>
              <label>Going out/Partywear (%) <span class="text-sm text-gray-500">(e.g., cocktail dresses, tuxedos)</span></label>
              <input type="number" name="Wardrobe_Going_out" min="0" max="100" value="0" class="wardrobe-percent input-field w-full" required>
            </div>
            <div>
              <label>Casual Wear (%) <span class="text-sm text-gray-500">(e.g., t-shirts, jeans)</span></label>
              <input type="number" name="Wardrobe_Casual" min="0" max="100" value="0" class="wardrobe-percent input-field w-full" required>
            </div>
            <div>
              <label>Formals/Semi-formals (%) <span class="text-sm text-gray-500">(e.g., suits, blazers)</span></label>
              <input type="number" name="Wardrobe_Formals" min="0" max="100" value="0" class="wardrobe-percent input-field w-full" required>
            </div>
            <div>
              <label>Ethnic/Indo-western (%) <span class="text-sm text-gray-500">(e.g., sarees, kurtas)</span></label>
              <input type="number" name="Wardrobe_Ethnic" min="0" max="100" value="0" class="wardrobe-percent input-field w-full" required>
            </div>
            <div>
              <label>Others (incl. Nightwear) (%) <span class="text-sm text-gray-500">(e.g., pajamas, athletic wear)</span></label>
              <input type="number" name="Wardrobe_Others" min="0" max="100" value="0" class="wardrobe-percent input-field w-full" required>
            </div>
          </div>
          <p class="text-yellow-700 text-sm mt-4 hidden wardrobe-error">
            <i class="fas fa-exclamation-circle"></i> Percentages must sum to 100%.
          </p>
        </div>

        <!-- Going out/Partywear Section -->
        <div class="section-card category">
          <h2><span class="section-title-icon"><i class="fas fa-glass-cheers"></i></span>Going out/Partywear</h2>
          <p class="mb-5">Clothing for special occasions like parties or dinners (e.g., cocktail dresses, tuxedos).</p>
          <div class="mb-6">
            <p class="mb-4">Purchase Channel Split (total must be 100%). Round to: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%: *</p>
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
                <label class="block mb-1">Platforms like Myntra/Ajio</label>
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
                <label class="block mb-1">Brand Websites</label>
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
                <label class="block mb-1">D2C/Social Media</label>
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
                <label class="block mb-1">Offline (Malls and Stores)</label>
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
                <label class="block mb-1">Unorganised/Thrifted</label>
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
            <p class="text-yellow-700 text-sm mt-3 hidden error-message">
              <i class="fas fa-exclamation-circle"></i> The sum of channel percentages must be exactly 100%.
            </p>
          </div>
          <div>
            <p class="mb-4">List up to 5 brands you frequently buy for Going out/Partywear:</p>
            <div class="brand-inputs">
              <input type="text" name="Going_out_Brand1" class="input-field" placeholder="Brand 1">
              <input type="text" name="Going_out_Brand2" class="input-field" placeholder="Brand 2">
              <input type="text" name="Going_out_Brand3" class="input-field" placeholder="Brand 3">
              <input type="text" name="Going_out_Brand4" class="input-field" placeholder="Brand 4">
              <input type="text" name="Going_out_Brand5" class="input-field" placeholder="Brand 5">
            </div>
          </div>
        </div>

        <!-- Casual Wear Section -->
        <div class="section-card category">
          <h2><span class="section-title-icon"><i class="fas fa-tshirt"></i></span>Casual Wear</h2>
          <p class="mb-5">Everyday clothing for informal settings (e.g., t-shirts, jeans, sneakers).</p>
          <div class="mb-6">
            <p class="mb-4">Purchase Channel Split (total must be 100%). Round to: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%: *</p>
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
                    <td><input type="radio" name="Casual_Brand_Websites" value="casual_brand_websites_40" class="percent radio-input" id="40"></td>
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
                <label class="block mb-1">Platforms like Myntra/Ajio</label>
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
                <label class="block mb-1">Brand Websites</label>
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
                <label class="block mb-1">D2C/Social Media</label>
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
                <label class="block mb-1">Offline (Malls and Stores)</label>
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
                <label class="block mb-1">Unorganised/Thrifted</label>
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
            <p class="text-yellow-700 text-sm mt-3 hidden error-message">
              <i class="fas fa-exclamation-circle"></i> The sum of channel percentages must be exactly 100%.
            </p>
          </div>
          <div>
            <p class="mb-4">List up to 5 brands you frequently buy for Casual Wear:</p>
            <div class="brand-inputs">
              <input type="text" name="Casual_Brand1" class="input-field" placeholder="Brand 1">
              <input type="text" name="Casual_Brand2" class="input-field" placeholder="Brand 2">
              <input type="text" name="Casual_Brand3" class="input-field" placeholder="Brand 3">
              <input type="text" name="Casual_Brand4" class="input-field" placeholder="Brand 4">
              <input type="text" name="Casual_Brand5" class="input-field" placeholder="Brand 5">
            </div>
          </div>
        </div>

        <!-- Formals/Semi-formals Section -->
        <div class="section-card category">
          <h2><span class="section-title-icon"><i class="fas fa-briefcase"></i></span>Formals/Semi-formals</h2>
          <p class="mb-5">Professional clothing for workplaces or semi-formal events (e.g., suits, blazers).</p>
          <div class="mb-6">
            <p class="mb-4">Purchase Channel Split (total must be 100%). Round to: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%: *</p>
            <div class="channel-table overflow-x-auto">
              <table class="w-full table-auto border-collapse">
                <thead>
                  <tr>
                    <th class="text-sm">Channel</th>
                    <th class="text-sm">0%</th</th>
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
                    <td><input type="radio" name="Formals_Offline" value="formals_offline_80" class="percent radio-input" id="80"></td>
                    <td><input type="radio" name="Formals_Offline" value="100" class="percent radio-input" id="formals_offline_100"></td>
                  </tr>
                  <tr>
                    <td>Unorganised/Thrifted</td>
                    <td><input type="radio" name="Formals_Unorganised" value="formals_unorganised_0" class="percent radio-input" id="0" required checked></td>
                    <td><input type="radio" name="Formals_Unorganised" value="20" class="percent radio-input" id="formals_unorganised_20"></td>
                    <td><input type="radio" name="Formals_Unorganised" value="percent radio-input" id="formals_unorganised_40"></td>
                    <td><input type="radio" name="Formals_Unorganised" value="60" class="percent radio-input" id="formals_unorganised_60"></td>
                    <td><input type="radio" name="Formals_Unorganised" value="80" class="percent radio-input" id="formals_unorganised_80"></td>
                    <td><input type="radio" name="Formals_Unorganised" value="100" class="percent radio-input" id="formals_unorganised_100"></td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="channel-select">
              <div>
                <label class="block mb-1">Platforms like Myntra/Ajio</label>
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
                <label class="block mb-1">Brand Websites</label>
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
                <label class="block mb-1">D2C/Social Media</label>
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
                <label class="block mb-1">Offline (Malls and Stores)</label>
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
                <label class="block mb-1">Unorganised/Thrifted</label>
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
            <p class="text-yellow-700 text-sm mt-3 hidden error-message">
              <i class="fas fa-exclamation-circle"></i> The sum of channel percentages must be exactly 100%.
            </p>
          </div>
          <div>
            <p class="mb-4">List up to 5 brands you frequently buy for Formals/Semi-formals:</p>
            <div class="brand-inputs">
              <input type="text" name="Formals_Brand1" class="input-field" placeholder="Brand 1">
              <input type="text" name="Formals_Brand2" class="input-field" placeholder="Brand 2">
              <input type="text" name="Formals_Brand3" class="input-field" placeholder="Brand 3">
              <input type="text" name="Formals_Brand4" class="input-field" placeholder="Brand 4">
              <input type="text" name="Formals_Brand5" class="input-field" placeholder="Brand 5">
            </div>
          </div>
        </div>

        <!-- Ethnic/Indo-western Section -->
        <div class="section-card category">
          <h2><span class="section-title-icon"><i class="fas fa-sari"></i></span>Ethnic/Indo-western</h2>
          <p class="mb-5">Traditional or fusion clothing for cultural events (e.g., sarees, kurtas).</p>
          <div class="mb-6">
            <p class="mb-4">Purchase Channel Split (total must be 100%). Round to: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%: *</p>
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
                    <td><input type="radio" name="Ethnic_D2C" value="0" class="percent radio-input id="ethnic_d2c_0" required checked></td>
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
                    <td><input type="radio" name="Ethnic_Offline" value="80" id="ethnic_offline_80" class="percent radio-input"></td>
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
                <label class="block mb-1">Platforms like Myntra/Ajio</label>
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
                <label class="block mb-1">Brand Websites</label>
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
                <label class="block mb-1">D2C/Social Media</label>
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
                <label class="block mb-1">Offline (Malls and Stores)</label>
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
                <label class="block mb-1">Unorganised/Thrifted</label>
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
            <p class="text-yellow-700 text-sm mt-3 hidden error-message">
              <i class="fas fa-exclamation-circle"></i> The sum of channel percentages must be exactly 100%.
            </p>
          </div>
          <div>
            <p class="mb-4">List up to 5 brands you frequently buy for Ethnic/Indo-western:</p>
            <div class="brand-inputs">
              <input type="text" name="Ethnic_Brand1" class="input-field" placeholder="Brand 1">
              <input type="text" name="Ethnic_Brand2" class="input-field" placeholder="Brand 2">
              <input type="text" name="Ethnic_Brand3" class="input-field" placeholder="Brand 3">
              <input type="text" name="Ethnic_Brand4" class="input-field" placeholder="Brand 4">
              <input type="text" name="Ethnic_Brand5" class="input-field" placeholder="Brand 5">
            </div>
          </div>
        </div>

        <!-- Others (incl. Nightwear) Section -->
        <div class="section-card category">
          <h2><span class="section-title-icon"><i class="fas fa-bed"></i></span>Others (incl. Nightwear)</h2>
          <p class="mb-5">Miscellaneous clothing items like nightwear or athletic wear (e.g., pajamas, gym wear).</p>
          <div class="mb-6">
            <p class="mb-4">Purchase Channel Split (total must be 100%). Round to: 0%–10% → 0%, 11%–30% → 20%, 31%–50% → 40%, 51%–70% → 60%, 71%–90% → 80%, 91%–100% → 100%: *</p>
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
                <label class="block mb-1">Platforms like Myntra/Ajio</label>
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
                <label class="block mb-1">Brand Websites</label>
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
                <label class="block mb-1">D2C/Social Media</label>
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
                <label class="block mb-1">Offline (Malls and Stores)</label>
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
                <label class="block mb-1">Unorganised/Thrifted</label>
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
            <p class="text-yellow-700 text-sm mt-3 hidden error-message">
              <i class="fas fa-exclamation-circle"></i> The sum of channel percentages must be exactly 100%.
            </p>
          </div>
          <div>
            <p class="mb-4">List up to 5 brands you frequently buy for Others (incl. Nightwear):</p>
            <div class="brand-inputs">
              <input type="text" name="Others_Brand1" class="input-field" placeholder="Brand 1">
              <input type="text" name="Others_Brand2" class="input-field" placeholder="Brand 2">
              <input type="text" name="Others_Brand3" class="input-field" placeholder="Brand 3">
              <input type="text" name="Others_Brand4" class="input-field" placeholder="Brand 4">
              <input type="text" name="Others_Brand5" class="input-field" placeholder="Brand 5">
            </div>
          </div>
        </div>

        <div class="text-center">
          <button type="submit" id="submitBtn">Submit Survey</button>
        </div>
        
        <div class="form-footer">
          <p>Thank you for participating in the Fashion Wardrobe Survey!</p>
        </div>
      </form>
    </div>
  </div>

  <script>
    const form = document.getElementById('surveyForm');
    const scriptURL = 'https://script.google.com/macros/s/AKfycbyrZdlq1Kf3C3Cv67tfjQVWELhqkxNSpKClTq29Wb1yZNriauWuuFnrci-sg4Rm7ODJ/exec';
    const MOBILE_BREAKPOINT = 640;

    // Synchronize radio buttons and dropdowns
    function syncInputs(source, targetClass) {
      const name = source.name;
      const value = source.value || "0"; // Ensure 0 is treated as a valid value
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

      // Force DOM update by triggering input event
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
          initializeInputs(); // Re-initialize inputs after form reset
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
