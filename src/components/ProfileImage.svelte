<script>
    import { onMount } from "svelte";

    let container;
    let flip = false;
  
    function toggleFlip() {
      flip = !flip;
    }
  
    onMount(() => {
      const floatInterval = setInterval(() => {
        container.classList.toggle("float");
      }, 2000);
  
      return () => clearInterval(floatInterval);
    });
  </script>
  
  <style>
    .container {
      perspective: 1000px;
      width: 300px;
      height: 200px;
      border-radius: 50%;
      margin-top: 1.5rem;
      position: relative;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);

    }
  
    .profile-image {
      backface-visibility: hidden;
      border-radius: 50%;
      height: 100%;
      position: absolute;
      transition: transform 1s;
      width: 100%;
    }
  
    .back {
      background-color: rgba(0, 0, 0, 0.1);
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      transform: rotateY(180deg);
    }
  
    .app-icons {
      display: flex;
      justify-content: space-around;
      width: 100%;
    }
  
    .app-icons a {
      color: inherit;
      text-decoration: none;
    }
  
    .container.flip .front {
      transform: rotateY(180deg);
    }
  
    .container.flip .back {
      transform: rotateY(0);
    }
  
    .container.float {
      animation: float 2s ease-in-out infinite;
    }
  
    @keyframes float {
      0%, 100% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-10px);
      }
    }
  </style>
  
  <div class="container" bind:this="{container}" on:click="{toggleFlip}">
    <img
      src="https://alantaijournal.weebly.com/uploads/1/4/0/0/140039658/dsc00908-900x600-4_orig.jpg"
      alt="Profile"
      class="profile-image front"
    />
    <div class="profile-image back">
      <div class="app-icons">
        <a href="https://www.facebook.com" target="_blank" rel="noopener noreferrer">Facebook</a>
        <a href="https://www.twitter.com" target="_blank" rel="noopener noreferrer">Twitter</a>
        <a href="https://www.instagram.com" target="_blank" rel="noopener noreferrer">Instagram</a>
      </div>
    </div>
  </div>
  