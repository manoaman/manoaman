<!-- PortfolioSection.svelte -->
<script>
    // Your TypeScript code here
    // Assuming project data is an array of objects
    let projects = [
      { 
        title: 'Project 1', 
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris suscipit dolor eget urna dictum pharetra.'
      },
      { 
        title: 'Project 2', 
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris suscipit dolor eget urna dictum pharetra.'
      },
      // Add more project objects as needed
    ];
  </script>
  
  <section id="portfolio">
    <div class="container">
      <h2>Portfolio</h2>
      <div class="row">
        {#each projects as project}
          <div class="col-md-4 mb-4">
            <div class="card">
              <img src="https://via.placeholder.com/350x150" class="card-img-top" alt="...">
              <div class="card-body">
                <h5 class="card-title">{project.title}</h5>
                <p class="card-text">{project.description}</p>
                <a href="#" class="btn btn-primary">Learn More</a>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
  
  <style>
    /* Picocss styles for the portfolio section */
    /* Custom CSS */
    @import 'style.css';
  </style>
  