<div class="landing">
	<nav />
	<div id="main">
		<div id="main-text">
			<p id="hi">hi, my name is</p>
			<p id="name">alex verić</p>
			<hr id="line" />
			<p id="desc1"><b>Mechatronics Engineering</b> student at University of Waterloo</p>
			<p id="desc2">software and robotics enthusiast</p>
		</div>

		<div id="socials">
			<div id="socials-grid">
				<div class="socials-links" id="linkedin">
					<a href="https://www.linkedin.com/in/alex-veric-aa4a26259/"
						><img class="socials-img" src="/Images/linkedin.png" alt="LinkedIn Icon" /></a
					>
				</div>
				<div class="socials-links" id="instagram">
					<a href="https://www.instagram.com/alex.veric/"
						><img class="socials-img" src="/Images/instagram.png" alt="Instagram Icon" /></a
					>
				</div>
				<div class="socials-links" id="github">
					<a href="https://github.com/JogaFish"
						><img class="socials-img" src="/Images/github.png" alt="Github Icon" /></a
					>
				</div>
				<div class="socials-links" id="email">
					<a href="mailto:alexvericweb@gmail.com"
						><img class="socials-img" src="/Images/email.png" alt="Email Icon" /></a
					>
				</div>
			</div>
		</div>
	</div>
	<div id="view">
		<div id="view-grid">
			<div class="view-grids">
				<a href="#project-anchor">View my projects</a>
			</div>
			<div class="view-grids">
				<div id="arrow">
					<img src="/Images/arrow.png" alt="Arrow" />
				</div>
			</div>
		</div>
	</div>
</div>

<style>
	.landing {
		font-family: 'Inter', sans-serif;
		color: white;
		display: grid;
		height: auto;
		grid-template-columns: 0.7fr 0.3fr;
		grid-template-rows: 0.2fr 1.5fr;
		grid-template-areas:
			'nav nav'
			'main view';
		grid-gap: 0.2rem;
	}
	nav {
		grid-area: nav;
		/* background-color: #4AA9DE; */
		display: grid;
		grid-template-columns: repeat(12, 1fr);
	}
	#main {
		grid-area: main;
		/* background-color: #F96868; */
		padding-top: 0px;
		padding-left: 10vw;
		display: grid;
		grid-template-rows: 2fr 1fr;
	}
	#view {
		grid-area: view;
		/* background-color: #1DCB2E; */
		display: flex;
		justify-content: center;
		align-items: center;
	}
	#view-grid {
		/* background-color: black; */
		display: grid;
		grid-template-rows: 1fr 1fr;
	}
	.view-grids {
		display: flex;
		justify-content: center;
		align-items: center;
		/* background-color: blue; */
	}
	.view-grids a {
		text-decoration: none;
		color: white;
	}
	.view-grids a:hover {
		text-decoration: underline;
	}
	#main-text {
		padding-top: 10vh;
		/* background-color: green; */
		text-align: left;
	}
	#socials {
		/* background-color: blue; */
		display: flex;
		align-items: center;
	}
	#socials-grid {
		/* background-color: purple; */
		width: 225px;
		height: 56.25;
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 1rem;
	}
	img {
		max-width: 100%;
		max-height: 100%;
	}
	#hi {
		font-size: 22.5px;
		font-weight: regular;
	}
	#name {
		font-size: 78px;
		font-weight: bold;
		line-height: 0px;
		margin-top: 60px;
		margin-bottom: 70px;
	}
	#desc1 {
		margin-top: 30px;
		font-size: 18px;
		margin-bottom: 10px;
	}
	#desc2 {
		margin-top: 0px;
		font-size: 18px;
		padding: 0px;
	}
	#line {
		width: 40vw;
		margin-left: 0px;
		max-width: 600px;
		min-width: 500px;
		padding-bottom: 0px;
	}
	#arrow {
		width: 25px;
		height: 100px;
	}
</style>
