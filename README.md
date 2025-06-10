
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fashion Survey - Wardrobe Insights</title>
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
    .channel-container select {
      width: 100%;
      padding: 0.75rem;
      border: 1px solid #e5e7eb;
      border-radius: 0.5rem;
      background-color: #ffffff;
      font-size: 0.875rem;
      color: #374151;
    }
    .channel-container select:focus {
      border-color: #3b82f6;
      box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
      outline: none;
    }
    .channel-container > div {
      margin-bottom: 1rem;
    }
    .channel-container label {
      display: block;
      font-weight: 500;
      color: #374151;
      margin-bottom: 0.5rem;
    }
    .error-message, .wardrobe-error {
      font-size: 1rem;
      padding: 0.5rem;
      background-color: #fee2e2;
      border-radius: 0.5rem;
    }
  </style>
</head>
<body class="bg-gray-50 min-h-screen flex items-center justify-center p-4">
  <div class="form-container mx-auto p-8">
    <h1 class="text-3xl font-bold text-gray-800 mb-4 text-center">Fashion Survey - Wardrobe Insights</h1>
    <p class="text-gray-600 mb-6 text-center">let us uncover your fashion journey! Share your shopping habits, favorite brands, and wardrobe vibes in this quick survey. All fields marked with * are required, and your responses are 100% confidential.</p>
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
            <input type="text" name="Email" class="input-field w-full p-3 border border-gray-300 rounded-lg focus:outline-none" required>
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
          <div class="channel-container" data-category="Going_out"></div>
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
          <div class="channel-container" data-category="Casual"></div>
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
          <div class="channel-container" data-category="Formals"></div>
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
          <div class="channel-container" data-category="Ethnic"></div>
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
          <div class="channel-container" data-category="Others"></div>
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

      <!-- Submit Button -->
      <div class="text-center">
        <button type="submit" class="bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 transition duration-200">Submit Survey</button>
      </div>
    </form>
  </div>

  <script>
    // Replace this URL with the actual /exec URL after deploying the Google Apps Script
    const scriptURL = 'https://script.google.com/macros/s/AKfycbx18pbpszswuA-WvrwaZZy8-GWHTU1v_1zsZi-BHmopMYGrLuP3_E7lPQq3RcVSeHEU/exec';
    const form = document.getElementById('surveyForm');
    const wardrobeInputs = document.querySelectorAll('.wardrobe-percent');
    const wardrobeError = document.querySelector('.wardrobe-error');
    const categories = document.querySelectorAll('.category');
    const MOBILE_BREAKPOINT = 640;

    // Channel options and labels
    const channels = [
      { label: 'Platforms like Myntra/Ajio', name: 'Platforms' },
      { label: 'Brand Websites', name: 'Brand_Websites' },
      { label: 'D2C/Social Media', name: 'D2C' },
      { label: 'Offline (Malls and Stores)', name: 'Offline' },
      { label: 'Unorganised/Thrifted', name: 'Unorganised' }
    ];
    const percentages = [0, 20, 40, 60, 80, 100];

    // Store user selections to persist across view changes
    const userSelections = {
      Going_out: {},
      Casual: {},
      Formals: {},
      Ethnic: {},
      Others: {}
    };

    // Function to save current selections before regenerating UI
    function saveSelections() {
      categories.forEach(category => {
        const categoryName = category.querySelector('.channel-container').dataset.category;
        const inputs = category.querySelectorAll('.percent');
        inputs.forEach(input => {
          let value;
          if (input.tagName === 'INPUT' && input.checked) {
            value = parseInt(input.value) || 0;
          } else if (input.tagName === 'SELECT') {
            value = parseInt(input.value) || 0;
          } else {
            value = 0;
          }
          userSelections[categoryName][input.name] = value;
        });
      });
    }

    // Function to generate radio buttons (desktop view)
    function generateRadioButtons(container, categoryName) {
      const table = document.createElement('table');
      table.className = 'w-full table-auto border-collapse';

      // Create table header
      const thead = document.createElement('thead');
      const headerRow = document.createElement('tr');
      headerRow.innerHTML = `
        <th class="text-sm">Channel</th>
        ${percentages.map(p => `<th class="text-sm">${p}%</th>`).join('')}
      `;
      thead.appendChild(headerRow);
      table.appendChild(thead);

      // Create table body
      const tbody = document.createElement('tbody');
      channels.forEach(channel => {
        const row = document.createElement('tr');
        const name = `${categoryName}_${channel.name}`;
        row.innerHTML = `
          <td>${channel.label}</td>
          ${percentages.map(p => `
            <td>
              <input type="radio" name="${name}" value="${p}" class="percent" id="${categoryName.toLowerCase()}_${channel.name.toLowerCase()}_${p}">
            </td>
          `).join('')}
        `;
        tbody.appendChild(row);
      });
      table.appendChild(tbody);

      // Wrap table in a div for overflow handling
      const wrapper = document.createElement('div');
      wrapper.className = 'overflow-x-auto';
      wrapper.appendChild(table);

      container.innerHTML = '';
      container.appendChild(wrapper);

      // Restore selections
      Object.keys(userSelections[categoryName]).forEach(name => {
        const value = userSelections[categoryName][name];
        const input = container.querySelector(`input[name="${name}"][value="${value}"]`);
        if (input) input.checked = true;
      });
    }

    // Function to generate dropdowns (mobile view)
    function generateDropdowns(container, categoryName) {
      const div = document.createElement('div');
      channels.forEach(channel => {
        const name = `${categoryName}_${channel.name}`;
        const selectDiv = document.createElement('div');
        selectDiv.innerHTML = `
          <label>${channel.label}</label>
          <select name="${name}" class="percent" required>
            ${percentages.map(p => `
              <option value="${p}" ${p === 0 ? 'selected' : ''}>${p}%</option>
            `).join('')}
          </select>
        `;
        div.appendChild(selectDiv);
      });

      container.innerHTML = '';
      container.appendChild(div);

      // Restore selections
      Object.keys(userSelections[categoryName]).forEach(name => {
        const value = userSelections[categoryName][name];
        const select = container.querySelector(`select[name="${name}"]`);
        if (select) select.value = value;
      });
    }

    // Function to generate UI based on screen size
    function generateUI() {
      const isMobile = window.innerWidth <= MOBILE_BREAKPOINT;
      const containers = document.querySelectorAll('.channel-container');
      saveSelections(); // Save current selections before regenerating
      containers.forEach(container => {
        const categoryName = container.dataset.category;
        if (isMobile) {
          generateDropdowns(container, categoryName);
        } else {
          generateRadioButtons(container, categoryName);
        }
      });
    }

    // Initial generation and resize handling
    window.addEventListener('resize', generateUI);
    generateUI();

    // Form validation and submission
    function validateWardrobe() {
      let sum = 0;
      wardrobeInputs.forEach(input => {
        sum += parseInt(input.value) || 0;
      });
      console.log('Wardrobe Sum:', sum); // Debugging
      wardrobeError.classList.toggle('hidden', sum === 100);
      return sum === 100;
    }

    function validateCategoryPercentages(category) {
      const inputs = category.querySelectorAll('.percent');
      let sum = 0;
      inputs.forEach(input => {
        let value;
        if (input.tagName === 'INPUT' && input.checked) {
          value = parseInt(input.value) || 0;
        } else if (input.tagName === 'SELECT') {
          value = parseInt(input.value) || 0;
        } else {
          value = 0;
        }
        console.log('Input:', input.name, 'Value:', value); // Debugging
        sum += value;
      });
      console.log('Category Sum:', sum); // Debugging
      const errorMessage = category.querySelector('.error-message');
      errorMessage.classList.toggle('hidden', sum === 100);
      return sum === 100;
    }

    function validateForm() {
      const wardrobeValid = validateWardrobe();
      const categoriesValid = Array.from(categories).every(category => validateCategoryPercentages(category));
      const isValid = wardrobeValid && categoriesValid;
      console.log('Form Validation Result:', isValid); // Debugging
      return isValid;
    }

    form.addEventListener('submit', e => {
      e.preventDefault();
      console.log('Submit button clicked'); // Debugging
      if (validateForm()) {
        fetch(scriptURL, {
          method: 'POST',
          body: new FormData(form)
        })
        .then(response => {
          console.log('Fetch Response:', response); // Debugging
          return response.json();
        })
        .then(data => {
          console.log('Form Submission Success:', data); // Debugging
          alert('Thank you! Your survey has been submitted successfully.');
          form.reset();
          generateUI(); // Regenerate UI after reset
        })
        .catch(error => {
          console.error('Fetch Error:', error); // Debugging
          alert(`Error submitting form: ${error.message}. Please check your network connection and ensure the Google Apps Script is deployed correctly with the /exec endpoint.`);
        });
      } else {
        console.log('Validation failed, form not submitted.'); // Debugging
      }
    });
  </script>
</body>
</html>
