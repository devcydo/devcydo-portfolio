<script>
	import { library } from '@fortawesome/fontawesome-svg-core';
	import { faBars, faGlobe, faShieldAlt, faTimes, faHome, faUser, faFileAlt, faBriefcase, faPaperPlane, 
			faEnvelope, faAddressCard, faFilePdf, faGraduationCap, faAward, faCalendar, faArrowRight, faLaptopCode} from '@fortawesome/free-solid-svg-icons';
	import { faGithubSquare, faLinkedin } from '@fortawesome/free-brands-svg-icons';
	import { FontAwesomeIcon } from 'fontawesome-svelte';

	//Import lang
	import en from '../public/lang/en.json'
	import es from '../public/lang/es.json'
	//Custom components
	import SkillAccordion from './components/SkillAccordion.svelte'
	import ExperienceContent from './components/ExperienceContent.svelte'
	import SwiperComponent from './components/SwiperComponent.svelte'
	import ContactCard from './components/ContactCard.svelte'
	import { onMount } from 'svelte';
	//Modal
	import ProjectGallery from './components/ProjectGallery.svelte'
  	import Modal from './components/Modal.svelte';
	import Popup from './components/Popup.svelte';
	import { modal } from './components/stores.js';

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
	/* Lang */
	let _lang = "en"

	onMount(()=>{
		try {
			let lang = localStorage.getItem("lang")
			_lang = lang
			if(!lang) throw "no-data"
		} catch (error) {
			localStorage.setItem("lang", "en")
			_lang = "en"
		}
	})
	
	let lang = localStorage.getItem("lang")
	if(lang === "es") lang = es
	else lang = en

	/* == OFF CANVAS MENU  == */
	let toggleMenu = ''
	let tabTarget = 'education'

	let category4 = [
		lang.skills.category4_options.option1,
		lang.skills.category4_options.option2,
	]

	let category5 = [
		lang.skills.category5_options.option1,
		lang.skills.category5_options.option2,
		lang.skills.category5_options.option3,
		lang.skills.category5_options.option4,
		lang.skills.category5_options.option5,
		lang.skills.category5_options.option6,
		lang.skills.category5_options.option7
	]

	function reload() {
		try {
			let lang = localStorage.getItem("lang");
			if (!lang) throw "no-data";
			if (lang === "en") localStorage.setItem("lang", "es");
			else localStorage.setItem("lang", "en");
		} catch (error) {
			localStorage.setItem("lang", "en");
		}
		window.location.reload();
	}

</script>

<Modal show={$modal}>

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
					<button on:click={reload}>{lang.lang.spanish}</button>
					<button on:click={reload}>{lang.lang.english}</button>
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
						<FontAwesomeIcon icon="home"/> {lang.menu.home}
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#aboutme" class="nav_link"
					>
						<FontAwesomeIcon icon="user"/> {lang.menu.about_me}
					</a>
				</li>
				<li class="nav_item">
					<a
						on:click="{() => toggleMenu = ''}" 
						href="#skills" class="nav_link"
					>
						<FontAwesomeIcon icon="laptop-code"/> {lang.menu.skills}
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#experience" class="nav_link"
					>
						<FontAwesomeIcon icon="file-alt"/> {lang.menu.experience}
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#portfolio" class="nav_link"
					>
						<FontAwesomeIcon icon="briefcase"/> {lang.menu.projects}
					</a>
				</li>
				<li class="nav_item">
					<a 
						on:click="{() => toggleMenu = ''}" 
						href="#contactme" class="nav_link"
					>
						<FontAwesomeIcon icon="paper-plane"/> {lang.menu.contact_me}
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
					<a href="mailto: devcydo@raccoonsolutions.net" target="_blank" class="home_social_icon">
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
					<img class="profile_img" src="./img/home/me.jpeg" alt="Selfie">
				</div>

				<div class="home_data">
					<h1 class="home_title">
						{lang.home.greeting}
						<span class="home_title_color">{lang.home.name}</span>
					</h1>
					<h3 class="home_subtitle">{lang.home.description}</h3>
					
					<a href="#contactme" class="button button_flex button_home">
						{lang.home.contact} &nbsp<FontAwesomeIcon icon="address-card"/>
					</a>
				</div>
			</div>
		</div>
	</section>

	<!-- -- ABOUT ME -- -->
	<section class="about section" id="aboutme">
		<h2 class="section_title">{lang.about_me.title}</h2>
		<span class="section_subtitle">{lang.about_me.subtitle}</span>

		<div class="aboutme_container container grid">

			<div class="aboutme_data">
				<p class="aboutme_description">
					{lang.about_me.description}
				</p>

				<p class="aboutme_description">
					{lang.about_me.description2}
				</p>

				<div class="aboutme_info">
					<div>
						<span class="aboutme_info_title">{lang.about_me.age_description}</span>
						<span class="about_info_name">{lang.about_me.age_title1} <br> {lang.about_me.age_title2}</span>
					</div>

					<div>
						<span class="aboutme_info_title">{lang.about_me.nacionality_description}</span>
						<span class="about_info_name">{lang.about_me.nacionality_title}</span>
					</div>

					<div>
						<span class="aboutme_info_title">{lang.about_me.inlove_description}</span>
						<span class="about_info_name">{lang.about_me.inlove_title1}</span>
					</div>
				</div>

				<div class="aboutme_buttons">
					<a href={lang.about_me.cv_route} target="_blank" class="button button_flex">
						{lang.about_me.cv} &nbsp<FontAwesomeIcon icon="file-pdf"/>
					</a>
				</div>
				<div class="aboutme_buttons_desc">
					<span class="aboutme_button_description">{lang.contact_me.subtitle}</span>
				</div>
			</div>
		</div>                
	</section>

	<!-- -- SKILLS -- -->
	<section class="skills section" id="skills">
		<h2 class="section_title">{lang.skills.title}</h2>
		<span class="section_subtitle">{lang.skills.subtitle}</span>

		<div class="skills_container container grid">

			<SkillAccordion
				skillName = {lang.skills.category1}
				skills = {['Assembly (8086)','C/C++','C#','Java','JavaScript','Kotlin','PHP','Python','SQL']}
				imgs = {['./img/skills/assembly.png','./img/skills/cplusplus.png', './img/skills/csharp.png','./img/skills/java.png',
						'./img/skills/js.png','./img/skills/kotlin.png','./img/skills/php.svg','./img/skills/python.png',
						'./img/skills/sql.png']}
				icon = 'code'
			/>

			<SkillAccordion
				skillName = {lang.skills.category2}
				skills = {['Ajax', 'Bootstrap', 'Laravel', 'MariaDB', 'MySQL', 'NodeJS', 'PostgreSQL', 'React/React Native', 'Redis', 
						'SQL Server', 'Svelte', 'UIkit']}
				imgs = {['./img/skills/ajax.png','./img/skills/bootstrap.png','./img/skills/laravel.png','./img/skills/mariadb.png',
						'./img/skills/mysql.png','./img/skills/nodejs.png','./img/skills/postgresql.png','./img/skills/react.png',
						'./img/skills/redis.svg','./img/skills/sqlserver.png', './img/skills/svelte.png', './img/skills/uikit.svg']}
				icon = 'server'
			/>

			<SkillAccordion
				skillName = {lang.skills.category3}
				skills = {['Cisco Packet Tracer', 'Docker', 'Git', 'Hyper-V', 'KVM', 'Linux', 'Microsoft Office', 'TrueNAS', 'VirtualBox', 
						'VMware Workstation / VMware EsXi', 'Windows / Windows Server']}
				imgs = {['./img/skills/cisco.png','./img/skills/docker.png','./img/skills/git.png','./img/skills/hyperv.png',
				'./img/skills/kvm.png','./img/skills/linux.png','./img/skills/office.png','./img/skills/truenas.png',
				'./img/skills/virtualbox.png', './img/skills/vmware.png', './img/skills/windows.png']}
				icon = 'ellipsis-h'
			/>

			<SkillAccordion
				skillName = {lang.skills.category6}
				skills = {["Aircrack-ng", "Burpsuite", "John the reaper", "JoomScan", "Lynis", "Metasploit", "Nessus", "Nmap", "OpenVAS", 
				"WireShark", "Zphisher"]}
				icon = 'user-secret'
			/>

			<SkillAccordion
				skillName = {lang.skills.category4}
				skills = {category4}
				imgs = {['./img/skills/spanish.png','./img/skills/english.svg']}
				icon = 'language'
			/>

			<SkillAccordion
				skillName = {lang.skills.category5}
				skills = {category5}
				icon = 'eye'
			/>
		</div>
	</section>

	<!-- -- Experience -- -->
	<section class="experience section" id="experience">
		<h2 class="section_title">{lang.experience.title}</h2>
		<span class="section_subtitle">{lang.experience.subtitle}</span>

		<div class="experience_container container">
			<div class="experience_tabs">
				<div 
					on:click="{() => tabTarget = 'education'}"
					class="experience_button button_flex {tabTarget == 'education' ? 'experience_active' : ''}" data-target='#education'	
				>
					<FontAwesomeIcon icon="graduation-cap" class="experience_icon"/>
					{lang.experience.tab1}
				</div>

				<div 
					on:click="{() => tabTarget = 'work'}"
					class="experience_button button_flex {tabTarget == 'work' ? 'experience_active' : ''}" data-target="#work"
				>
					<FontAwesomeIcon icon="briefcase" class="experience_icon"/>
					{lang.experience.tab2}
				</div>
				
				<div 
					on:click="{() => tabTarget = 'courses'}"
					class="experience_button button_flex {tabTarget == 'courses' ? 'experience_active' : ''}" data-target="#courses"
				>
					<FontAwesomeIcon icon="award" class="experience_icon"/>
					{lang.experience.tab3}
				</div>
			</div>

			<div class="experience_sections">
				<ExperienceContent
					{tabTarget}
					type = 'education'
					info = {[
						{
							'name':	lang.experience.tab1_info.info1_title,
							'school': lang.experience.tab1_info.info1_description,
							'desc': '',
							'date': lang.experience.tab1_info.info1_date
						},
						{
							'name':	lang.experience.tab1_info.info2_title,
							'school': lang.experience.tab1_info.info2_description,
							'desc': '',
							'date': lang.experience.tab1_info.info2_date
						},
					]}
				/>

				<ExperienceContent
					{tabTarget}
					type = 'work'
					info = {[
						{
							'name':	lang.experience.tab2_info.info1_title,
							'school': lang.experience.tab2_info.info1_subtitle,
							'desc': lang.experience.tab2_info.info1_description,
							'date': lang.experience.tab2_info.info1_date
						},
						{
							'name':	lang.experience.tab2_info.info2_title,
							'school': lang.experience.tab2_info.info2_subtitle,
							'desc': lang.experience.tab2_info.info2_description,
							'date': lang.experience.tab2_info.info2_date
						}
					]}
				/>

				<ExperienceContent
					{tabTarget}
					type = 'courses'
					info = {[
						{
							'name':	lang.experience.tab3_info.info1_title,
							'school': lang.experience.tab3_info.info1_description,
							'desc': '',
							'date': lang.experience.tab3_info.info1_date
						},
						{
							'name':	lang.experience.tab3_info.info2_title,
							'school': lang.experience.tab3_info.info2_description,
							'desc': '',
							'date': lang.experience.tab3_info.info2_date
						},
						{
							'name':	lang.experience.tab3_info.info3_title,
							'school': lang.experience.tab3_info.info3_description,
							'desc': '',
							'date': lang.experience.tab3_info.info3_date
						},
					]}
				/>
			</div>
		</div>
	</section>

	<!-- -- PORTFOLIO -- -->
	<section class="portfolio section" id="portfolio">
		<h2 class="section_title">{lang.projects.title}</h2>
		<span class="section_subtitle">{lang.projects.subtitle}</span>

		<div class="portfolio_container container">
			<SwiperComponent
				slides = {[
					{
						'title': lang.projects.project1.title,
						'description': lang.projects.project1.description,
						'route': './img/portfolio/eltepetate.png',
						'link': 'http://aquata.raccoonsolutions.net'
					},
					{
						'title': lang.projects.project2.title,
						'description': lang.projects.project2.description,
						'route': './img/portfolio/mia.jpg',
						'link': 'https://www.morelia.tecnm.mx/mia/'
					},
					{
						'title': lang.projects.project3.title,
						'description': lang.projects.project3.description,
						'route': './img/portfolio/inii.jpg',
						'link': 'https://www.facebook.com/Diinco-103458568500925'
					}
				]}
			/>
		</div>
	</section>

	<section class="contactme section" id="contactme">
		<h2 class="section_title">{lang.contact_me.title}</h2>
		<span class="section_subtitle">{lang.contact_me.subtitle}</span>

		<div class="contactme_container container">
			<div class="contactme_content grid">
				<ContactCard
					title = {lang.contact_me.card1.title}
					description = {lang.contact_me.card1.description}
					icon = 'home'
				/>
				<ContactCard
					title = {lang.contact_me.card2.title}
					description = {lang.contact_me.card2.description}
					icon = 'envelope'
				/>
				<ContactCard
					title = {lang.contact_me.card3.title}
					description = {lang.contact_me.card3.description}
					icon = 'envelope'
				/>
				<ContactCard
					title = {lang.contact_me.card4.title}
					description = {lang.contact_me.card4.description}
					icon = 'linkedin'
				/>
				<ContactCard
					title = {lang.contact_me.card5.title}
					description = {lang.contact_me.card4.description}
					icon = 'github-square'
				/>
			</div>
		</div>

	</section>

	<!-- -- COOL FOOTER -- -->
	<footer class="footer section">
		<div class="footer_container bd-grid">
			<h1 class="footer_title">{lang.footer.name}</h1>
			<p class="footer_description">{lang.footer.description1}</p>
			<p class="footer_description">{lang.footer.description2}</p>

			<div class="footer_social">
				<a href="mailto: devcydo@raccoonsolutions.net" class="footer_link">
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
</Modal>