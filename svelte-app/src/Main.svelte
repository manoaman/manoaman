<script>
    import { Link } from 'svelte-routing';
  
    const scriptSources = [
        'assets/js/jquery.min.js',
        'assets/js/browser.min.js',
        'assets/js/breakpoints.min.js',
        'assets/js/util.js',
        'assets/js/main.js'
    ];
  </script>
  
  
  
  <style>
    /* Add your styles here */
  </style>

{#each scriptSources as src}
  <script src={src}></script>
{/each}
  
  <head>
    <title>Dimension by HTML5 UP</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
    <link rel="stylesheet" href="assets/css/main.css" />
    <noscript><link rel="stylesheet" href="assets/css/noscript.css" /></noscript>
  </head>  

  <body class="is-preload">
    <div id="wrapper">
    <!-- Header -->
    <header id="header">
      <div class="logo">
        <span class="icon fa-gem"></span>
      </div>
      <div class="content">
        <div class="inner">
          <Link to="/portfolio"><h1>Manoaman</h1></Link>            
          <p>A fully responsive site template designed by <a href="https://html5up.net">HTML5 UP</a> and released<br /> for free under the <a href="https://html5up.net/license">Creative Commons</a> license.</p>
        </div>
      </div>
      <nav>
        <ul>
          <li><a href="#intro">Intro</a></li>
          <li><a href="#work">Work</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>
  
    <!-- Main -->
    <div id="main">
      <!-- Intro -->
      <article id="intro">
        <h2 class="major">Intro</h2>
        <span class="image main"><img src="images/pic01.jpg" alt="" /></span>
        <p>Hey there, I'm thrilled to be an artist in creating stunning designs and innovative applications. My journey as a programmer spans across various projects, where I've woven magic through code. Let's embark on a journey of creativity and technology!</p>
      </article>
  
      <!-- Work -->
      <article id="work">
        <h2 class="major">Work</h2>
        <span class="image main"><img src="images/pic02.jpg" alt="" /></span>
        <p>Welcome to my realm of cool designs and groundbreaking applications! Here, you'll discover a fusion of creativity and functionality. Dive into a world where pixels meet purpose, and aesthetics merge with usability.</p>
      </article>
  
      <!-- About -->
      <article id="about">
        <h2 class="major">About</h2>
        <span class="image main"><img src="images/pic03.jpg" alt="" /></span>
        <p>Get ready to explore a journey defined by passion, creativity, and a relentless pursuit of excellence. At the heart of my work lies the mission to craft extraordinary experiences that bring joy and satisfaction. Join me on this exhilarating venture!</p>
      </article>
  
      <!-- Contact -->
      <article id="contact">
        <h2 class="major">Contact</h2>
        <form method="post" action="#">
          <!-- Contact form fields can be added here -->
        </form>
        <ul class="icons">
          <!-- Contact icons and links can be added here -->
        </ul>
      </article>
  
      <!-- Elements -->
      <article id="elements">
        <!-- Various HTML elements and sections can be added here -->
      </article>
    </div>
  
    <!-- Footer -->
    <footer id="footer">
      <p class="copyright">&copy; Untitled. Design: <a href="https://html5up.net">HTML5 UP</a>.</p>
    </footer>
  </div>
  
  <!-- BG -->
  <div id="bg"></div>  

  </body>