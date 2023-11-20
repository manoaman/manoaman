<!-- Portfolio.svelte -->
<script>
  import Navbar from './Navbar.svelte';
  import Header from './Header.svelte';
  import PortfolioSection from './PortfolioSection.svelte';
  // import SearchableList from './SearchableList.svelte';
  import Autocomplete from './Autocomplete.svelte';

  const myJsonData = {
  "BasketballSkills": {
    "Shooting": [
      "Jump shot",
      "Layups",
      "Free throws",
      "Three-pointers",
      "Mid-range shots",
      "Fadeaways"
    ],
    "BallHandling": [
      "Dribbling with both hands",
      "Crossover dribble",
      "Behind-the-back dribble",
      "Between-the-legs dribble",
      "Spin moves"
    ],
    "Passing": [
      "Chest pass",
      "Bounce pass",
      "Overhead pass",
      "No-look pass",
      "Alley-oop pass"
    ],
    "Rebounding": [
      "Offensive rebounding",
      "Defensive rebounding",
      "Boxing out",
      "Tip-ins"
    ],
    "Defense": [
      "On-ball defense",
      "Off-ball defense",
      "Blocking shots",
      "Stealing the ball",
      "Defensive positioning"
    ],
    "Footwork": [
      "Pivot moves",
      "Jab steps",
      "Euro step",
      "Post moves"
    ],
    "Conditioning": [
      "Endurance training",
      "Agility drills",
      "Speed training",
      "Strength training"
    ],
    "GameStrategy": [
      "Understanding plays",
      "Offensive and defensive positioning",
      "Reading the game flow",
      "Teamwork and communication"
    ],
    "SpecializedSkills": [
      "Pick and roll execution",
      "Screen setting",
      "Fast break execution",
      "Setting up plays"
    ],
    "MentalSkills": [
      "Focus and concentration",
      "Decision making under pressure",
      "Confidence building",
      "Resilience and handling failures"
    ]
  }
  };    
</script>  

<main>
  <!-- <SearchableList />     -->
  <Autocomplete jsonData={myJsonData['BasketballSkills']} />    
  <Navbar />
  <Header />
  <PortfolioSection />
</main>

<style>
  /* Global Picocss styles or styles for the main layout */  
</style>