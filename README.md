<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta name="description" content="Umang Kumar - Computer Science student, developer and creative problem solver.">
	<title>Umang Kumar | Portfolio</title>
	<style>
		:root {
			--ink: #f3f7f2;
			--muted: #a7b4b0;
			--bg: #101715;
			--bg-soft: #17211e;
			--card: rgba(29, 41, 37, 0.78);
			--lime: #d9ff62;
			--coral: #ff765f;
			--cyan: #70e7dc;
			--line: rgba(243, 247, 242, 0.14);
		}

		* { box-sizing: border-box; }

		html { scroll-behavior: smooth; }

		body {
			margin: 0;
			background: var(--bg);
			color: var(--ink);
			font-family: "Trebuchet MS", "Arial Narrow", sans-serif;
			line-height: 1.55;
			overflow-x: hidden;
		}

		body::before {
			position: fixed;
			inset: 0;
			z-index: -1;
			background-image: linear-gradient(rgba(255,255,255,.025) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.025) 1px, transparent 1px);
			background-size: 44px 44px;
			content: "";
			mask-image: linear-gradient(to bottom, black, transparent 80%);
		}

		a { color: inherit; }

		.shell { width: min(1180px, calc(100% - 40px)); margin: auto; }

		nav {
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 26px 0;
		}

		.logo { color: var(--lime); font-size: 1.25rem; font-weight: 900; letter-spacing: .08em; text-decoration: none; }
		.logo span { color: var(--coral); }
		.nav-links { display: flex; gap: 26px; color: var(--muted); font-size: .84rem; }
		.nav-links a { text-decoration: none; }
		.nav-links a:hover { color: var(--lime); }

		.hero {
			display: grid;
			grid-template-columns: 1.1fr .9fr;
			align-items: center;
			min-height: 650px;
			gap: 50px;
			padding: 55px 0 90px;
		}

		.eyebrow { color: var(--lime); font-size: .75rem; font-weight: 900; letter-spacing: .19em; text-transform: uppercase; }
		h1 { max-width: 730px; margin: 18px 0 24px; font-size: clamp(3.5rem, 9vw, 8.7rem); letter-spacing: -.07em; line-height: .88; }
		h1 em { color: var(--coral); font-style: normal; }
		.hero-copy { max-width: 570px; color: var(--muted); font-size: 1.08rem; }
		.actions { display: flex; flex-wrap: wrap; gap: 14px; margin-top: 34px; }
		.button { display: inline-block; padding: 13px 20px; border: 1px solid var(--lime); color: var(--bg); background: var(--lime); font-size: .82rem; font-weight: 900; text-decoration: none; transition: transform .2s, box-shadow .2s; }
		.button:hover { box-shadow: 6px 6px 0 var(--coral); transform: translate(-3px, -3px); }
		.button.ghost { border-color: var(--line); color: var(--ink); background: transparent; }

		.hero-art { position: relative; min-height: 430px; perspective: 1100px; }
		.hero-art::before { position: absolute; inset: 8% 7% 10% 9%; border: 1px solid var(--line); content: ""; transform: rotate(8deg); }
		.orbit { position: absolute; top: 12%; right: 10%; width: 340px; height: 340px; border: 1px solid rgba(112,231,220,.42); border-radius: 50%; transform: rotate(-24deg); }
		.orbit::after { position: absolute; top: 8px; left: 50%; width: 13px; height: 13px; border-radius: 50%; background: var(--coral); box-shadow: 0 0 25px var(--coral); content: ""; }
		.profile-plate { position: absolute; top: 20%; left: 13%; width: 76%; padding: 30px; background: linear-gradient(145deg, #29433d, #15211e); border: 1px solid rgba(255,255,255,.24); box-shadow: 18px 20px 0 rgba(217,255,98,.18), 0 30px 60px rgba(0,0,0,.34); transform: rotateY(-13deg) rotateX(8deg) rotateZ(-5deg); }
		.profile-plate::before { display: block; width: 85px; height: 85px; margin-bottom: 56px; border: 9px solid var(--lime); border-radius: 50%; background: var(--coral); content: ""; box-shadow: 26px 18px 0 var(--cyan); }
		.profile-plate h2 { margin: 0; font-size: clamp(2rem, 4vw, 3.5rem); line-height: .95; }
		.profile-plate p { margin: 12px 0 0; color: var(--muted); }
		.plate-tag { position: absolute; right: 22px; bottom: 22px; color: var(--lime); font-size: .72rem; letter-spacing: .12em; }

		.section { padding: 90px 0; border-top: 1px solid var(--line); }
		.section-heading { display: flex; align-items: end; justify-content: space-between; gap: 30px; margin-bottom: 34px; }
		.section-heading h2 { margin: 0; font-size: clamp(2rem, 5vw, 4rem); letter-spacing: -.05em; line-height: .95; }
		.section-heading p { max-width: 390px; margin: 0; color: var(--muted); }
		.number { color: var(--coral); font-size: .75rem; font-weight: 900; letter-spacing: .15em; }

		.project-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; }
		.project { min-height: 280px; padding: 26px; background: var(--card); border: 1px solid var(--line); transition: transform .25s, border-color .25s; }
		.project:hover { border-color: var(--lime); transform: translateY(-10px) rotateX(3deg) rotateY(-3deg); }
		.project:nth-child(2) { margin-top: 35px; }
		.project:nth-child(3) { margin-top: 70px; }
		.project-index { color: var(--lime); font-size: .78rem; font-weight: 900; }
		.project h3 { margin: 44px 0 12px; font-size: 1.55rem; }
		.project p { color: var(--muted); font-size: .91rem; }
		.project-link { display: inline-block; margin-top: 12px; color: var(--cyan); font-size: .78rem; font-weight: 900; text-decoration: none; }

		.about-grid { display: grid; grid-template-columns: .9fr 1.1fr; gap: 70px; }
		.skill-list { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
		.skill { padding: 18px; border-left: 3px solid var(--coral); background: var(--bg-soft); }
		.skill strong { display: block; margin-bottom: 10px; }
		.bar { height: 4px; background: #31423d; }
		.bar span { display: block; height: 100%; background: var(--lime); }
		.timeline { position: relative; padding-left: 28px; border-left: 1px solid var(--coral); }
		.timeline-item { position: relative; margin-bottom: 34px; }
		.timeline-item::before { position: absolute; top: 8px; left: -34px; width: 10px; height: 10px; border: 3px solid var(--bg); border-radius: 50%; background: var(--lime); content: ""; }
		.timeline-item small { color: var(--coral); font-weight: 900; letter-spacing: .08em; }
		.timeline-item h3 { margin: 7px 0 3px; }
		.timeline-item p { margin: 0; color: var(--muted); }

		.contact-band { display: flex; align-items: center; justify-content: space-between; gap: 30px; padding: 42px; background: var(--lime); color: var(--bg); }
		.contact-band h2 { max-width: 570px; margin: 0; font-size: clamp(2rem, 5vw, 4.4rem); letter-spacing: -.06em; line-height: .9; }
		.contact-actions { display: flex; flex-wrap: wrap; gap: 12px; }
		.contact-band .button { border-color: var(--bg); background: var(--bg); color: var(--lime); white-space: nowrap; }
		.contact-band .button.ghost { border-color: var(--bg); color: var(--bg); }
		footer { display: flex; justify-content: space-between; padding: 28px 0; color: var(--muted); font-size: .8rem; }

		@media (max-width: 760px) {
			.shell { width: min(100% - 28px, 560px); }
			.nav-links { display: none; }
			.hero, .about-grid { grid-template-columns: 1fr; }
			.hero { min-height: auto; padding: 60px 0 90px; }
			.hero-art { min-height: 360px; }
			.orbit { width: 260px; height: 260px; }
			.profile-plate { left: 5%; width: 88%; }
			.project-grid { grid-template-columns: 1fr; }
			.project:nth-child(2), .project:nth-child(3) { margin-top: 0; }
			.contact-band, footer { align-items: flex-start; flex-direction: column; }
		}

		@media (prefers-reduced-motion: reduce) {
			* { scroll-behavior: auto !important; transition: none !important; }
		}
	</style>
</head>
<body>
	<div class="shell">
		<nav>
			<a class="logo" href="#top">UK<span>.</span></a>
			<div class="nav-links"><a href="#work">Work</a><a href="#about">About</a><a href="monu.html">Resume</a><a href="#contact">Contact</a></div>
		</nav>

		<header class="hero" id="top">
			<div>
				<div class="eyebrow">Computer Science Student / Builder</div>
				<h1>Ideas into <em>useful</em> things.</h1>
				<p class="hero-copy">I am Umang Kumar, a motivated developer from Bihar currently studying Computer Science at IES University, Bhopal. I enjoy learning fast and building technology that solves real problems.</p>
				<div class="actions"><a class="button" href="#work">Explore my work</a><a class="button ghost" href="monu.html">View my resume</a></div>
			</div>
			<div class="hero-art" aria-label="Abstract profile illustration">
				<div class="orbit"></div>
				<div class="profile-plate"><span class="plate-tag">AVAILABLE TO LEARN</span><h2>UMANG<br>KUMAR</h2><p>Developer in progress. Problem solver by nature.</p></div>
			</div>
		</header>

		<section class="section" id="work">
			<div class="section-heading"><div><div class="number">01 / SELECTED PROJECTS</div><h2>Things I have<br>been building.</h2></div><p>Small experiments, academic work and practical ideas that keep me curious.</p></div>
			<div class="project-grid">
				<article class="project"><div class="project-index">01</div><h3>Science O Holic</h3><p>A science-focused project presenting useful concepts in a simple and approachable format.</p><a class="project-link" href="mailto:umangkumar953@gmail.com?subject=Science%20O%20Holic">DISCUSS PROJECT +</a></article>
				<article class="project"><div class="project-index">02</div><h3>Home Automation</h3><p>An automation concept for controlling and managing home devices through a connected system.</p><a class="project-link" href="mailto:umangkumar953@gmail.com?subject=Home%20Automation">DISCUSS PROJECT +</a></article>
				<article class="project"><div class="project-index">03</div><h3>Object Detection</h3><p>A computer-vision project exploring how images and video can identify objects intelligently.</p><a class="project-link" href="mailto:umangkumar953@gmail.com?subject=Object%20Detection">DISCUSS PROJECT +</a></article>
			</div>
		</section>

		<section class="section" id="about">
			<div class="section-heading"><div><div class="number">02 / THE FOUNDATION</div><h2>Curious mind.<br>Steady work.</h2></div><p>My current focus is growing strong technical fundamentals while becoming a better teammate and communicator.</p></div>
			<div class="about-grid">
				<div class="skill-list">
					<div class="skill"><strong>Communication</strong><div class="bar"><span style="width: 82%"></span></div></div>
					<div class="skill"><strong>Teamwork</strong><div class="bar"><span style="width: 88%"></span></div></div>
					<div class="skill"><strong>Problem solving</strong><div class="bar"><span style="width: 76%"></span></div></div>
					<div class="skill"><strong>Learning mindset</strong><div class="bar"><span style="width: 95%"></span></div></div>
				</div>
				<div class="timeline">
					<div class="timeline-item"><small>2023 — PRESENT</small><h3>B.Tech in Computer Science & Engineering</h3><p>IES University, Bhopal · Current CGPA: 7.86</p></div>
					<div class="timeline-item"><small>COMPLETED</small><h3>Diploma in Electronics & Communication</h3><p>IES College of Technology, Bhopal · 82%</p></div>
					<div class="timeline-item"><small>ACADEMIC BASE</small><h3>Class 10th · BSEB</h3><p>Utkramit M.S. Goasi, Bihar · 60%</p></div>
				</div>
			</div>
		</section>

		<section class="section" id="contact"><div class="contact-band"><h2>Have a problem worth solving?</h2><div class="contact-actions"><a class="button" href="mailto:umangkumar953@gmail.com">Email Umang →</a><a class="button ghost" href="monu.html">Open resume</a></div></div></section>
		<footer><span>© 2026 Umang Kumar</span><span>Goasi · Bihar · India</span><a href="mailto:umangkumar953@gmail.com">umangkumar953@gmail.com</a></footer>
	</div>
</body>
</html>
