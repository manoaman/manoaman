<!-- PortfolioSection.svelte -->
<script>
    let projects = [
        { 
            title: 'Basketball adult', 
            description: 'Experience the thrill of competitive basketball leagues for adults. Join us to play, compete, and have fun on the court.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Basketball+adult',
            url: '/basketball-adult'            
        },
        { 
            title: 'Basketball youth', 
            description: 'Calling all young basketball enthusiasts! Engage in exciting youth basketball programs designed to develop skills and foster teamwork.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Basketball+youth',
            url: '/basketball-youth'
        },
        { 
            title: 'Movies and Books', 
            description: 'Explore a collection of captivating movies and thought-provoking books. Discover new stories that entertain and inspire.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Movies+and+Books',
            url: '/movies-and-books'
        },
        { 
            title: 'Technology', 
            description: 'Stay updated with the latest advancements in technology. From gadgets to innovations, dive into the world of cutting-edge tech.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Technology',
            url: '/technology'
        },
        { 
            title: 'Los Angeles', 
            description: 'Discover the vibrant culture, diverse neighborhoods, and iconic landmarks in the City of Angels. Experience the essence of Los Angeles.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Los+Angeles',
            url: '/los-angeles'            
        },
        { 
            title: 'Kyoto', 
            description: 'Immerse yourself in the rich history and serene beauty of Kyoto. Explore ancient temples, traditional culture, and scenic landscapes.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Kyoto',
            url: '/kyoto'            
        },
        { 
            title: 'Cool stuffs', 
            description: 'An eclectic mix of fascinating things! From intriguing inventions to unique hobbies, explore a variety of cool and interesting stuff.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Cool+stuffs',
            url: '/cools-stuffs'            
        },
        { 
            title: 'CSS playground', 
            description: 'Dive into the world of CSS creativity! Explore and experiment with various CSS techniques and designs in this interactive playground.',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=CSS+playground',
            url: '/css-playground'
        },
        { 
            title: 'Random', 
            description: 'Discover a collection of random and diverse content. From intriguing facts to captivating visuals, expect the unexpected!',
            imageUrl: 'https://via.placeholder.com/350x150/AAAAAA/FFFFFF/?text=Random',
            url: '/random'            
        }  
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
              <img src={project.imageUrl} class="card-img-top" alt="Placeholder Image">
              <div class="card-body">
                <h5 class="card-title">{project.title}</h5>
                <p class="card-text">{project.description}</p>
                <a href={project.url} class="btn btn-primary">Learn More</a>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>
  
  
  <style>
    .card {
        border: 1px solid #ddd;
        border-radius: 5px;
        padding: 15px;
        margin-bottom: 20px;
        background-color: #f9f9f9;
    }
    
    .card img {
        width: 100%;
        height: auto;
        border-radius: 5px;
    }
    
    .card-title {
        font-size: 1.5em;
        margin-bottom: 10px;
    }
    
    .card-text {
        font-size: 1.1em;
        color: #555;
    }
    
    .btn-primary {
        background-color: #007bff;
        color: #fff;
        border: none;
        padding: 8px 16px;
        border-radius: 4px;
        text-decoration: none;
    }
    
    .btn-primary:hover {
        background-color: #0056b3;
    }
  </style>
  