<script>
	import { name } from '$lib/constants';
</script>

<svelte:head>
	<title>Ma Estate</title>
    <link rel="icon" type="image/x-icon" href="/img/favicon.ico">
</svelte:head>

<header>
	<nav class="navbar">
		<a href="/" class="logo">{name}</a>
		<!-- <a href="/">Home</a> -->
		<a class="navbar-right" href="/#properties">Properties</a>
		<a class="navbar-right" href="/#features">Features</a>
		<a class="navbar-right" href="/a/">About</a>
	</nav>
</header>

<main>
	<slot />
</main>


<footer>
	<p contenteditable="true">&copy; 2025 {name}. Copying Ma homework will result in sussy Ma activities.</p>
</footer>

<style>

	@font-face {
		font-family: 'DM Sans';
		src: url('/fonts/DM_Sans/DMSans-VariableFont_opsz,wght.ttf') format('truetype');
		font-weight: 100 1000;
		font-style: normal;
	}

	@font-face {
		font-family: 'DM Sans';
		src: url('/fonts/DM_Sans/DMSans-Italic-VariableFont_opsz,wght.ttf') format('truetype');
		font-weight: 100 1000;
		font-style: italic;
	}

	@font-face {
		font-family: 'DM Serif Display';
		src: url('/fonts/DM_Serif_Display/DMSerifDisplay-Regular.ttf') format('truetype');
		font-weight: 400;
		font-style: normal;
	}

	@font-face {
		font-family: 'DM Serif Display';
		src: url('/fonts/DM_Serif_Display/DMSerifDisplay-Italic.ttf') format('truetype');
		font-weight: 400;
		font-style: italic;
	}

	:root {

		--primary-color: rgb(67, 35, 35);
		--primary-color-transparent: rgba(67, 35, 35, 0.4);
		--primary-color-transparent-light: rgba(67, 35, 35, 0.075);


		--secondary-color: rgb(47, 87, 85);
		--secondary-color-transparent: rgba(47, 87, 85, 0.8);

		--third-color: rgb(90, 150, 144);

		--fourth-color: rgb(224, 217, 217);
		--fourth-color-transparent: rgba(224, 217, 217, 0.6);
		--fourth-color-darker: rgb(219, 212, 212);
		--fourth-color-brighter: rgb(229, 222, 222);

		--fifth-color: rgb(35, 76, 106);

		font-size: 16px;

		margin: 0;
		padding: 0;

		overflow-x: hidden;

		scroll-behavior: smooth;

		scrollbar-color: var(--third-color) var(--fourth-color);
  		scrollbar-width: thin;
	}

	

	:global(body) {
		margin: 0;
		font-family: 'DM Sans', sans-serif;
		background-color: black;
		color: var(--primary-color);
	}

	:global(h1, h2) {
		font-family: 'DM Serif Display';
		letter-spacing: -1px;
	}

	@media (width < 768px) {
			:root {
				font-size: 12px;
		}
	}

	header {
		position: fixed;
		background-color: var(--secondary-color-transparent);
		backdrop-filter: blur(16px);
		padding: 1rem 0;
		color: white;
		z-index: 9999;
		width: 100%;
		height: 24px;
	}

	.navbar {
		display: flex;
		justify-content: space-between;
		align-items: center;
		gap: 4rem;
		margin: 0 4dvw;
	}

	@media (width < 768px) {
		.navbar {
			gap: 1.75rem;
		}
	}

	.navbar a {
		text-decoration: none;
		color: inherit;
		font-size: 1.25rem;
		text-wrap: nowrap;
	}
	
	.logo {
		color: var(--primary-color);
		margin-right: auto;
		font-weight: 600;
	}

	main {
		padding: 0;
		margin: 0 auto;
	}

	footer {
		text-align: center;
		padding: 2rem;
		background-color: var(--secondary-color);
		color: white;
		font-size: 1.25rem;
	}

	/* First Section Styling */

	:global(.first-section) {
		display: flex;
		/* height: 864px; */
		height: 100vh;
		min-height: 512px;
		max-height: 1080px;
		width: 100%;
		margin: 0;
	}

	:global(.first-section::before) {
		content: "";
    	position: absolute;
		inset: 0;
    	background: linear-gradient(90deg, 
     		rgba(0, 0, 0, 0) 0%, 
			rgba(67, 35, 35, 0) 48%, 
    		rgba(67, 35, 35, 0.6) 75%, 
    	    rgba(67, 35, 35, 0.8) 100%
    	);
		height: 1296px;
    	z-index: -1;
	}

	:global(.fs-content-right) {
		position: absolute;
		color: white;
		top: 20%;
		right: 7.5%;
		text-align: right;
		font-size: 4rem;
		line-height: 0.75;
		width: 800px;
		/* border: 10px solid black; */
	}

	@media (width < 1112px) {
		:global(.fs-content-right) {
			font-size: 3rem;
		}
	}

	@media (width < 768px) {
		:global(.fs-content-right) {
			font-size: 2.75rem;
		}
	}

	:global(.fs-content-right p) {
		opacity: 0.8;
		font-size: 1rem;
		text-align: center;
	}

	/* Looked worse than expected...
	@keyframes clipReveal {
		from {
			clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
		}
		to {
			clip-path: polygon(0 0, 95% 0, 70% 100%, 0% 100%);
		}
	}
	*/

	@keyframes revealImage {
		0% {
			filter: saturate(0%);
			opacity: 0;
		}
		50% {
			filter: saturate(100%);
		}
		100% {
			opacity: 1;
		}
	}

	:global(.first-section .bg-image) {
		position: absolute;
		width: 100%;
    	height: 100vh;
		min-height: 512px;
		max-height: 1080px;
		object-fit: cover;
		background-size: cover;
		background-repeat: no-repeat;
		/* clip-path: polygon(0 0, 95% 0, 70% 100%, 0% 100%); */
		/* animation: clipReveal 2s ease-in-out 0s forwards; */
		animation: revealImage 1500ms ease-in;
		/* transition: all 2500ms ease-in; */
		z-index: -2;
	}

	/* Second Section Styling */

	:global(.second-section) {
		background-color: var(--fourth-color);
		color: var(--primary-color);
		display: flex;
		justify-content: center;
		transition: all 1s ease;
	}

	:global(.second-section-blank) {
		color: var(--primary-color);
	}

	:global(.ss-content) {
		color: inherit;
		margin: 0 auto;
		width: 90%;
	}

	:global(.ss-content h2) {
		font-size: 4rem;
		margin-top: 64px;
	}

	:global(.ss-content p) {
		font-size: 1.25rem;
	}

	@media (width > 768px) {
		:global(.ss-content h2, .ss-content p) {
			padding: 0 5%;
		}
	}

	:global(.ma-stuff-grid) { 
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-items: flex-start;
		gap: 1.75dvw;
		margin: 0 auto;
    }

    :global(.ma-stuff-item) {
		position: relative;
        display: inline-block;
		width: 36dvw;
		/* height: calc(389px + 12dvw); */
		height: fit-content;
        break-inside: avoid;
        padding: 24px;
		background: var(--fourth-color-brighter);
        border-radius: 16px;
        }

	/* :global(.neumorphism) {
		box-shadow: 18px 18px 48px #c5c5c5,
        			-18px -18px 48px #fbfbfb;
	} */
	
	:global(.neumorphism) {
		box-shadow: -8px -8px 24px 0px rgba(255, 255, 255, 0.5), 8px 8px 24px 0px rgba(0, 0, 0, 0.10);
		border: 2px solid var(--primary-color-transparent-light);
	}

	/*
	:global(.ma-stuff-item .view-button) {
		bottom: 24px;
	}
	*/

	:global(.ma-stuff-item .button-container) {
    	position: absolute;
    	bottom: 24px;
    	display: flex;
    	gap: 16px;
	}

		:global(.caption-inline) { 
			display: flex;
			justify-content: space-between;
			align-items: center;
			padding-top: 12px;
			text-wrap: nowrap;
		}

        :global(.caption) { 
			font-size: 1.5rem !important;
			line-height: 1.5;
			margin: auto 0;
			padding: 4px 8px;
			opacity: 0.9;
		}

		:global(.caption-price) {
			font-size: 2.25rem !important;
			margin: 0;
			padding: 4px 8px !important;
			opacity: 0.9;
		}

		:global(h3.caption) { 
			font-size: 2.25rem !important;
			padding: 0 8px;
		}

		:global(p.caption) {
			margin-bottom: 84px;
			padding: 0 8px !important;
		}

		:global(.responsive-media) { 
			width: 100%; 
			height: auto;
			object-fit: cover;
			display: block;
			margin: 0 auto;
			border-radius: 16px;
			animation: revealImage 2000ms ease-in 0s;
		}

		@media (width < 1216px) {

			:global(.ma-stuff-grid) {
				justify-content: center;
				gap: 32px;
			}

			:global(.ma-stuff-item) {
				width: 77dvw;
				/* height: calc(198px + 38dvw); */
				height: fit-content;
				display: block;
			}

			:global(p.caption) {
				margin-bottom: 144px;
			}

			:global(.responsive-media) {
				width: 100%;
				height: auto;
				max-height: 384px;
			}

			:global(.ma-stuff-item .button-container) {
    			position: absolute;
    			bottom: 24px;
				left: 50%;
				transform: translateX(-50%);
    			display: flex;
				flex-direction: column;
				justify-content: center;
				align-items: center;
				width: calc(77dvw - 36px);
    			gap: clamp(8px, 12px, 24px);
			}
		}

		@media (width > 768px) and (width < 1216px) {
			:global(p.caption) {
				margin-bottom: 168px;
			}
		}

		@media (width < 768px) {
			:global(.ma-stuff-item) {
				padding: 16px;
				width: 84dvw;
			}

			:global(.ma-stuff-item .button-container) {
				width: calc(84dvw - 28px);
			}
		}

		:global(.ma-stuff-item-small) {
			position: relative;
			width: 664px;
			height: fit-content; /* 589px */
        	break-inside: avoid;
        	padding: 24px;
			margin: auto;
			background: var(--fourth-color-brighter);
        	border-radius: 16px;
			transition: all 300ms ease;
			display: flex;
    		gap: 8px;
			/* animation: neumorphism 3000ms cubic-bezier(0.2, 0, 0.8, 1) forwards; */
        }

		:global(.ma-stuff-item-small:hover) {
			background: var(--primary-color);
			color: white;
			box-shadow: none;
		}

		:global(.responsive-media-small) { 
			width: 336px;
			height: 232px;
			object-fit: cover;
			display: inline-block;
			margin: 0;
			border-radius: 16px;
			animation: revealImage 2000ms ease-in 0s;
		}

		:global(.caption-small) { 
			font-size: 1.5rem;
			margin: 0 0 0 16px;
			opacity: 0.9;
		}

		:global(.caption-price-small) {
			font-size: 1.5rem;
			margin: 0 0 6px 16px;
			opacity: 0.9;
		}

		:global(h3.caption-small) { 
			font-size: 3rem;
			line-height: 1;
		}

		:global(.button-container-small) {
    	position: absolute;
    	bottom: 24px;
		margin: 0 12px;
    	display: flex;
    	gap: clamp(12px, 24px, 42px);
	}

	@media (width < 1528px) {
		:global(.ma-stuff-item-small) {
			width: 100%;
			box-sizing: border-box;
		}

		:global(.responsive-media-small) {
			width: clamp(216px, 36dvw, 624px);
			height: auto;
		}

		:global(h3.caption-small) {
			margin: 8px 0 0 16px;
		}

		:global(.caption-small) {
			word-wrap: break-word;
			overflow-wrap: break-word;
		}
	}

	@media (width < 768px) {
		:global(.ma-stuff-item-small) {
			width: 93.48% !important;
			padding: 16px;
			gap: 0;
			width: 84dvw;
		}

		:global(.responsive-media-small) {
			width: clamp(16px, 26dvw, 624px);
			height: auto;
		}
	}

        /* :global(.responsive-media:hover) {
            transform: scale(1.1);
            top: 50%;
            left: 50%;
        } */

	:global(.third-section) {
		background-color: var(--fourth-color);
		/* background: linear-gradient(0deg,rgba(0, 0, 0, 1) 25%, rgba(224, 217, 217, 1) 100%); */
		color: var(--primary-color);
		display: flex;
		justify-content: center;
		transition: all 1s ease;
	}

	:global(.third-section-blank) {
		color: var(--fifth-color);
		display: flex;
		justify-content: center;
	}

	:global(.ts-content) {
		height: fit-content;
		color: inherit;
		margin: 0 auto;
		width: 90%;
	}

	

	:global(.ts-content h2) {
		font-size: 4rem;
		margin-top: 64px;
	}

	@media (width > 768px) {
		:global(.ts-content h2, .ts-content p) {
			padding: 0 5%;
		}

		:global(.caption-small) {
			padding: 0 !important;
		}
	}

	:global(.content-details) {
		margin-top: -32px;
		margin-bottom: 48px;
		font-size: 1.5rem !important;
	}

	:global(.ts-content-grid) {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		align-items: center;
		gap: 1.75dvw;
		margin: 0 auto 64px;
	}

	:global(.ma-stuff-item-small-feature) {
		position: relative;
		width: clamp(406px, 36dvw, 36dvw);
		height: calc(512px - 16dvw); /* 589px 289px */
        break-inside: avoid;
        padding: 24px;
		margin: auto;
		background: var(--fourth-color-brighter);
        display: flex;
        border-radius: 16px;
    }

	:global(.responsive-media-small-feature) {
		width: clamp(128px, 14dvw, 256px);
		border-radius: 16px;
		height: 100%;
		object-fit: cover;
	}

	@media (width < 1112px) {
		:global(.ma-stuff-item-small-feature) {
			width: 77dvw;
			height: calc(392px - 24dvw); /* 320px */
		}

		:global(.responsive-media-small-feature) {
			width: clamp(128px, 36dvw, 256px);
			height: 100%;
		}
	}

	@media (width < 768px) {
		:global(.ma-stuff-item-small-feature) {
			width: 84dvw;
			padding: 16px;
		}
	}

	:global(.ts-content p) {
		line-height: 1.5;
	}
</style>
