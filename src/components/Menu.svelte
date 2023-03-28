<script>
    let showWritingDropdown = false;
  
    function toggleWritingDropdown() {
      showWritingDropdown = !showWritingDropdown;
    }
  </script>
  
  <style>
    .menu {
      display: flex;
      justify-content: space-around;
      align-items: center;
      background-color: #f0f0f0;
      padding: 1rem;
      font-family: 'Roboto', sans-serif;
    }
  
    .name {
      font-size: 2rem;
      text-transform: uppercase;
      flex: 1;
      text-align: center;
      font-family: 'Pacifico', cursive;
    }
  
    .nav-items {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex: 2;
    }
  
    .nav-item {
      position: relative;
    }
  
    .nav-item:hover .dropdown {
      display: block;
    }
  
    .nav-link {
      text-decoration: none;
      color: #333;
      padding: 0.5rem 1rem;
    }
  
    .nav-link:hover {
      color: #555;
    }
  
    .dropdown {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      min-width: 150px;
      background-color: #f0f0f0;
      padding: 1rem;
      box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
      z-index: 100;
    }
  
    .dropdown-item {
      display: block;
      padding: 0.25rem 0;
    }
  </style>
  
  <div class="menu">
    <div class="name">Alan Tai</div>
    <nav class="nav-items">
      <a href="#" class="nav-link">Home</a>
      <div class="nav-item" on:mouseenter={toggleWritingDropdown} on:mouseleave={toggleWritingDropdown}>
        <a href="#" class="nav-link">Writing</a>
        {#if showWritingDropdown}
        <div class="dropdown">
          <a href="#" class="nav-link dropdown-item">Features</a>
          <a href="#" class="nav-link dropdown-item">Opinion</a>
          <a href="#" class="nav-link dropdown-item">Sports</a>
          <a href="#" class="nav-link dropdown-item">News</a>
          <a href="#" class="nav-link dropdown-item">A&E</a>
          <a href="#" class="nav-link dropdown-item">Misc</a>
        </div>
        {/if}
      </div>
      <a href="#" class="nav-link">Photography</a>
      <a href="#" class="nav-link">Design</a>
      <a href="#" class="nav-link">Multimedia</a>
    </nav>
  </div>
  