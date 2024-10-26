<script>
	import { onMount } from 'svelte';
  
	function typeWriter(element, text, speed) {
	  let i = 0;
	  function type() {
		if (i < text.length) {
		  element.innerHTML += text.charAt(i);
		  i++;
		  setTimeout(type, speed);
		}
	  }
	  type();
	}
  
	onMount(() => {
	  const title = document.querySelector('.title');
	  const aboutText = document.querySelector('.about-text');
	  typeWriter(title, "About Me", 100);
	  typeWriter(aboutText, "Hi, I'm [Your Name]. I'm a [Your Profession]. I love coding, designing, and creating amazing web experiences.", 50);
	});
  </script>
  
  <main>
	<section class="about-me">
	  <h1 class="title pixel-text"></h1>
	  <p class="about-text pixel-text"></p>
	</section>
	<div class="social-media">
	  <a href="https://github.com/yourusername" target="_blank">GitHub</a>
	  <a href="https://instagram.com/yourusername" target="_blank">Instagram</a>
	  <a href="https://twitter.com/yourusername" target="_blank">X</a>
	  <a href="https://discord.com/yourusername" target="_blank">Discord</a>
	</div>
  </main>
  
  <style>
	main {
	  display: flex;
	  flex-direction: column;
	  justify-content: center;
	  align-items: center;
	  height: 100vh;
	  text-align: center;
	  position: relative;
	  background-color: black; 
	  color: white; 
	}
	.about-me {
	  z-index: 1;
	}
	.pixel-text {
	  font-family: 'Press Start 2P', cursive;
	  font-size: 2rem;
	}
	.about-text {
	  font-size: 1.5rem;
	  margin: 1rem 0;
	}
	.social-media {
	  display: flex;
	  justify-content: center;
	  gap: 1rem;
	  margin-top: 1rem;
	  position: absolute;
	  bottom: 1rem;
	}
	.social-media a {
	  text-decoration: none;
	  color: inherit;
	  font-family: 'Press Start 2P', cursive;
	  font-size: 1rem;
	}
  </style>
