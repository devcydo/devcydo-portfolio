<script>
	import { library } from '@fortawesome/fontawesome-svg-core';
	import { faBars, faGlobe, faShieldAlt, faTimes, faHome, faUser, faFileAlt, faBriefcase, faPaperPlane, 
			faEnvelope, faAddressCard, faFilePdf, faGraduationCap, faAward, faCalendar, faArrowRight, faLaptopCode} from '@fortawesome/free-solid-svg-icons';
	import { faGithubSquare, faLinkedin } from '@fortawesome/free-brands-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

	//Custom components
	import SkillAccordion from './components/SkillAccordion.svelte'
	import ExperienceContent from './components/ExperienceContent.svelte'
	import SwiperComponent from './components/SwiperComponent.svelte'
	import ContactCard from './components/ContactCard.svelte'
	//General icons
	library.add(faBars);
	library.add(faGlobe);
	library.add(faShieldAlt);
	library.add(faTimes);
	library.add(faHome);
	library.add(faUser);
	library.add(faFileAlt);
	library.add(faBriefcase);
	library.add(faPaperPlane);
	library.add(faEnvelope);
	library.add(faAddressCard);
	library.add(faFilePdf);
	library.add(faGraduationCap);
	library.add(faAward);
	library.add(faCalendar);
	library.add(faArrowRight);
	library.add(faLaptopCode);
	//Brand Icons
	library.add(faGithubSquare);
	library.add(faLinkedin);

	/* == OFF CANVAS MENU  == */
	let toggleMenu = ''
	let tabTarget = 'education'
</script>

<header class="header" id="header">
	<nav class="nav bd_grid">
		<div on:click="{() => toggleMenu = 'show'}" 
			class="nav_toggle" 
			id="nav-toggle"
		>
			<FontAwesomeIcon icon="bars"/>
		</div>

		<div class="right_nav">                    
			<!-- Dropdown -->
			<div class="dropdown ">
				<FontAwesomeIcon icon="globe" class="dropdown_logo"/>
				<div class="dropdown_content">
					<button>English</button>
					<button>Spanish</button>
				</div>
			</div>

			<FontAwesomeIcon icon="shield-alt" class="nav_icon"/>			
			<a href="./index.html" class="nav_logo">devcydo</a>
		</div>

		<div class="nav_menu {toggleMenu != '' ? 'show' : ''}"  id="nav-menu">
			<div on:click="{() => toggleMenu = ''}"
				class="nav_close" 
				id="nav-close"
			>
				<FontAwesomeIcon icon="times"/>
			</div>

			<ul class="nav_list">
				<li class="nav_item">
					<a
						on:click="{() => toggleMenu = ''}" 
						href="#home" class="nav_link"
					>
						<FontAwesomeIcon icon="home"/> Home
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#aboutme" class="nav_link"
					>
						<FontAwesomeIcon icon="user"/> About me
					</a>
				</li>
				<li class="nav_item">
					<a
						on:click="{() => toggleMenu = ''}" 
						href="#skills" class="nav_link"
					>
						<FontAwesomeIcon icon="laptop-code"/> Skills
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#experience" class="nav_link"
					>
						<FontAwesomeIcon icon="file-alt"/> Experience
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#portfolio" class="nav_link"
					>
						<FontAwesomeIcon icon="briefcase"/> Projects
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#contactme" class="nav_link"
					>
						<FontAwesomeIcon icon="paper-plane"/> Contact me
					</a>
				</li>
			</ul>
		</div>
	</nav>
</header>

<main class="main" id="main">
	<!-- -- HOME -- -->
	<section class="home section" id="home">
		<div class="home_container container grid">
			<div class="home_content grid">
				<div class="home_social">
					<a href="mailto: devcydo@gmail.com" target="_blank" class="home_social_icon">
						<FontAwesomeIcon icon='envelope'/>	
					</a>

					<a href="https://www.linkedin.com/in/devcydo" target="_blank" class="home_social_icon">
						<FontAwesomeIcon icon={['fab', 'linkedin']}/>	
					</a>
					
					<a href="https://github.com/devcydo" target="_blank" class="home_social_icon">
						<FontAwesomeIcon icon={['fab', 'github-square']}/>			
					</a>
				</div>

				<div class="home_img">
					<img class="profile_img" src="./img/home/me.jpg" alt="Selfie">
				</div>

				<div class="home_data">
					<h1 class="home_title">
						Hi, I am 
						<span class="home_title_color">Luis Eduardo Martínez Morales</span>
					</h1>
					<h3 class="home_subtitle">Fullstack developer and cybersecurity enthusiast</h3>
					
					<a href="#contactme" class="button button_flex button_home">
						Contact me &nbsp<FontAwesomeIcon icon="address-card"/>
					</a>
				</div>
			</div>
		</div>
	</section>

	<!-- -- ABOUT ME -- -->
	<section class="about section" id="aboutme">
		<h2 class="section_title">About me</h2>
		<span class="section_subtitle">My introduction</span>

		<div class="aboutme_container container grid">

			<div class="aboutme_data">
				<p class="aboutme_description">
					I am currently a 9th semester student of the Computer Systems Engineering career at Tecnológico Nacional de México, Campus Morelia (also known
					as Instituto Tecnológico de Morelia) with a specialty in Information Security. I consider myself a responsible, enthusiastic and committed 
					developer, who likes challenges and learning new things every day.
				</p>

				<p class="aboutme_description">
					I love to code, but also I am into cybersecurity, server configurations and pentesting. 
				</p>

				<div class="aboutme_info">
					<div>
						<span class="aboutme_info_title">22</span>
						<span class="about_info_name">Years <br> old</span>
					</div>

					<div>
						<span class="aboutme_info_title">MX</span>
						<span class="about_info_name">Nacionality</span>
					</div>

					<div>
						<span class="aboutme_info_title">Python</span>
						<span class="about_info_name">In love <br> with</span>
					</div>
				</div>

				<div class="aboutme_buttons">
					<a href="./pdf/Practica3.pdf" target="_blank" class="button button_flex">
						View CV &nbsp<FontAwesomeIcon icon="file-pdf"/>
					</a>
				</div>
			</div>
		</div>                
	</section>

	<!-- -- SKILLS -- -->
	<section class="skills section" id="skills">
		<h2 class="section_title">Skills</h2>
		<span class="section_subtitle">My technical skills and interests</span>

		<div class="skills_container container grid">

			<SkillAccordion
				skillName = 'Programming Languages'
				skills = {['Javascript','Python','PHP','SQL','C/C++','C#','Java','Kotlin','Assembly (8086)']}
				icon = 'code'
			/>

			<SkillAccordion
				skillName = 'Development Technologies'
				skills = {['Laravel','React','React Native','Svelte', 'Node JS','MySQL','MariaDB','SQL Server',
							'PostgreSQL','Ajax','Bootstrap','UIkit']}
				icon = 'server'
			/>

			<SkillAccordion
				skillName = 'Other Technologies'
				skills = {['Git','Virtualization','Docker','Windows/Windows Server','Linux','Microsoft Office']}
				icon = 'ellipsis-h'
			/>

			<SkillAccordion
				skillName = 'Languages'
				skills = {['Spanish (First language)','English (Advanced)']}
				icon = 'language'
			/>

			<SkillAccordion
				skillName = 'Personal interests'
				skills = {['Cybersecurity','Operative Systems','Server configurations', 'Databases', 'Virtualization', 
							'Containers (Docker / Kubernetes)']}
				icon = 'eye'
			/>
		</div>
	</section>

	<!-- -- Experience -- -->
	<section class="experience section" id="experience">
		<h2 class="section_title">Experience</h2>
		<span class="section_subtitle">What I've been doing</span>

		<div class="experience_container container">
			<div class="experience_tabs">
				<div 
					on:click="{() => tabTarget = 'education'}"
					class="experience_button button_flex {tabTarget == 'education' ? 'experience_active' : ''}" data-target='#education'	
				>
					<FontAwesomeIcon icon="graduation-cap" class="experience_icon"/>
					Education
				</div>

				<div 
					on:click="{() => tabTarget = 'work'}"
					class="experience_button button_flex {tabTarget == 'work' ? 'experience_active' : ''}" data-target="#work"
				>
					<FontAwesomeIcon icon="briefcase" class="experience_icon"/>
					Work
				</div>
				
				<div 
					on:click="{() => tabTarget = 'courses'}"
					class="experience_button button_flex {tabTarget == 'courses' ? 'experience_active' : ''}" data-target="#courses"
				>
					<FontAwesomeIcon icon="award" class="experience_icon"/>
					 Courses
				</div>
			</div>

			<div class="experience_sections">
				<ExperienceContent
					{tabTarget}
					type = 'education'
					info = {[
						{
							'name':'Computer Systems Engineering',
							'school': 'Tecnológico Nacional de México, Campus Morelia',
							'desc': '',
							'date': 'Aug 2017 - Today'
						},
						{
							'name':'Information Security (Degree specialty)',
							'school': 'Tecnológico Nacional de México, Campus Morelia',
							'desc': '',
							'date': 'Aug 2020 - Today'
						}
					]}
				/>

				<ExperienceContent
					{tabTarget}
					type = 'work'
					info = {[
						{
							'name':'Fullstack developer',
							'school': 'Freelancer',
							'desc': 'I helped to develop a CRM software for a construction company',
							'date': 'Apr 2021 - Sep 2021'
						},
						{
							'name':'Backend developer',
							'school': 'INII Inversiones Inmobiliarias',
							'desc': 'Currently working on a super secret project!',
							'date': 'Oct 2021 - Today'
						}
					]}
				/>

				<ExperienceContent
					{tabTarget}
					type = 'courses'
					info = {[
						{
							'name':'Introduction to Cybersecurity',
							'school': 'Cisco Networking Academy',
							'desc': '',
							'date': 'Nov 2020 - Dec 2020'
						},
						{
							'name':'Basic principles of routing and switching',
							'school': 'Cisco Networking Academy',
							'desc': '',
							'date': 'Aug 2020 - Feb 2021'
						},
						{
							'name':'CCNA Routing and Switching: Scaling Networks',
							'school': 'Cisco Networking Academy',
							'desc': '',
							'date': 'Aug 2020 - Feb 2021'
						}
					]}
				/>
			</div>
		</div>
	</section>

	<!-- -- PORTFOLIO -- -->
	<section class="portfolio section" id="portfolio">
		<h2 class="section_title">Projects</h2>
		<span class="section_subtitle">Take a look at some of my work!</span>

		<div class="portfolio_container container">
			<SwiperComponent
				slides = {[
					{
						'title': 'AQUATA',
						'description': 'Begin as a school project and turned into a real solution. My team and I developed a CRM Software for a real client that owns a trout farm, he needed a digital tool that helped him to manage the incomes, expenses, sales, ponds and stages of his trouts.',
						'route': './img/portfolio/blueprint.png',
						'link': ''
					},
					{
						'title': 'Maestría en Ingeniería Administrativa',
						'description': "Informative website about the master's degree in administrative engineering of the Instituto Tecnológico de Morelia ",
						'route': './img/portfolio/mia.jpg',
						'link': ''
					},
					{
						'title': 'INII Inversiones Inmobiliarias',
						'description': 'Actually working on a super secret project that will be anounced soon!',
						'route': './img/portfolio/inii.jpg',
						'link': ''
					}
				]}
			/>
		</div>
	</section>

	<section class="contactme section" id="contactme">
		<h2 class="section_title">Contact me!</h2>
		<span class="section_subtitle">Get in touch with me by any of these social media</span>

		<div class="contactme_container container">
			<div class="contactme_content grid">
				<ContactCard
					title = 'Location'
					description = 'Morelia, Mich.'
					icon = 'home'
				/>
				<ContactCard
					title = 'Mail'
					description = 'devcydo@gmail.com'
					icon = 'envelope'
				/>
				<ContactCard
					title = 'LinkedIn'
					description = 'https://www.linkedin.com/in/devcydo'
					icon = 'linkedin'
				/>
				<ContactCard
					title = 'Github'
					description = 'https://github.com/devcydo'
					icon = 'github-square'
				/>
			</div>
		</div>

	</section>

	<!-- -- COOL FOOTER -- -->
	<footer class="footer section">
		<div class="footer_container bd-grid">
			<h1 class="footer_title">Luis Eduardo Martinez Morales</h1>
			<p class="footer_description">Devcydo personal portfolio</p>
			<p class="footer_description">Developed with Svelte</p>

			<div class="footer_social">
				<a href="mailto: devcydo@gmail.com" class="footer_link">
					<FontAwesomeIcon icon="envelope"/>
				</a>
				<a href="https://www.linkedin.com/in/devcydo" class="footer_link">
					<FontAwesomeIcon icon={['fab','linkedin']}/>
				</a>
				<a href="https://github.com/devcydo" class="footer_link">
					<FontAwesomeIcon icon={['fab','github-square']}/>
				</a>
			</div>
		</div>
	</footer>
</main>