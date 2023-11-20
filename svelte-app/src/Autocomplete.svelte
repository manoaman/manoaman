<!-- Autocomplete.svelte -->
<script>
    export let jsonData = {};
    let userInput = '';
    let showAutocomplete = false;
    let selectedItemIndex = -1;
    let listRef;
    let isUsingKeyboard = false;
  
    function filterItems(event) {
      userInput = event.target.value.toLowerCase();
      showAutocomplete = true;
      selectedItemIndex = -1; // Reset selected item index when filtering items
      isUsingKeyboard = false; // Reset keyboard usage when typing
    }
  
    function selectItem(category, item) {
      userInput = `${category}: ${item}`;
      showAutocomplete = false;
    }
  
    function handleKeyPress(event) {
      if (event.key === 'ArrowUp') {
        event.preventDefault(); // Prevent moving cursor in input field
        isUsingKeyboard = true;
        selectedItemIndex = Math.max(selectedItemIndex - 1, -1);
      } else if (event.key === 'ArrowDown') {
        event.preventDefault(); // Prevent moving cursor in input field
        isUsingKeyboard = true;
        selectedItemIndex = Math.min(selectedItemIndex + 1, filteredItems.length - 1);
      } else if (event.key === 'Enter' && selectedItemIndex !== -1) {
        const { category, item } = filteredItems[selectedItemIndex];
        selectItem(category, item);
      }
    }
  
    function setActiveItem(index) {
      if (isUsingKeyboard) {
        selectedItemIndex = index;
      }
    }
  
    function resetActiveItem() {
      selectedItemIndex = -1;
    }
  
    // Compute filtered items based on user input
    $: filteredItems = Object.entries(jsonData)
      .flatMap(([category, items]) => {
        category = category.toLowerCase();
        return items
          .filter(item => {
            item = item.toLowerCase();
            return item.includes(userInput) || category.includes(userInput);
          })
          .map(item => ({
            category,
            item
          }));
      });
  
    function highlightMatch(text) {
      const index = text.toLowerCase().indexOf(userInput);
      if (index !== -1) {
        const beforeMatch = text.slice(0, index);
        const matchText = text.slice(index, index + userInput.length);
        const afterMatch = text.slice(index + userInput.length);
        return `${beforeMatch}<strong>${matchText}</strong>${afterMatch}`;
      }
      return text;
    }
  </script>
  
  <!-- Styles remain unchanged -->
<!-- Styles -->
<style>
    /* Autocomplete styles */
    .autocomplete {
      position: relative;
      width: 300px;
      font-family: Arial, sans-serif;
    }
  
    input[type="text"] {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
      outline: none;
    }
  
    .autocomplete-items {
      position: absolute;
      top: 100%;
      left: 0;
      z-index: 99;
      border: 1px solid #d4d4d4;
      border-top: none;
      background-color: #fff;
      max-height: 300px; /* Adjust the max height as needed */
      overflow-y: auto;
      border-radius: 0 0 4px 4px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      min-width: 100%; /* Width adjusts based on content */
    }
  
    .autocomplete-item {
      padding: 10px;
      cursor: pointer;
      transition: background-color 0.3s ease;
      white-space: nowrap;
    }
  
    .autocomplete-item:hover {
      background-color: #f9f9f9;
    }
  
    .autocomplete-active {
      background-color: DodgerBlue !important;
      color: #ffffff;
    }
  
    .highlight {
      font-weight: bold;
    }
  </style>
  
  
  <!-- Svelte component -->
  <div class="autocomplete">
    <input
      type="text"
      name="myProject"
      placeholder="Search"
      on:input={filterItems}
      bind:value={userInput}
      on:keydown={handleKeyPress}
      on:blur={resetActiveItem}
    />
  
    {#if showAutocomplete && userInput !== '' && filteredItems.length > 0}
      <!-- Display autocomplete items -->
      <div
        class="autocomplete-items"
        tabindex="0"
        bind:this={listRef}
        on:blur={resetActiveItem}
      >
        {#each filteredItems as { category, item }, index}
          <div
            tabindex="0"
            on:click={() => selectItem(category, item)}
            on:mouseenter={() => setActiveItem(index)}
            class="autocomplete-item {selectedItemIndex === index && 'autocomplete-active'}"
            class:autocomplete-active={selectedItemIndex === index}
            style="white-space: nowrap;"
          >
            {@html highlightMatch(`${category}: ${item}`)}
          </div>
        {/each}
      </div>
    {/if}
  </div>
  