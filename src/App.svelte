
<script>

    // Having a poke around in the code? Good! Feel free to ask me any questions via email :)
    // mailto:harrison@phillingham.com

    import Navbar from './Navbar.svelte';
    import Home from './Home.svelte';
    import About from './About.svelte';
    import Skills from './Skills.svelte';
    import Current from './Current.svelte';
    import Projects from "./Projects.svelte";
    import Contact from "./Contact.svelte";
    import Footer from './Footer.svelte';


</script>

<div class = 'main_container'>

    <Home/>

    <About/>

    <Skills/>

    <Current />

    <Projects/>

    <Contact/>

    <Footer/>

    <Navbar/>

</div>


<style>

    :global(body) {
        font-family: "Poppins", sans-serif;
        background: #0e0e0e;
        user-select: none;
        min-height: 110%;
    }

    .main_container{
        max-width: 1920px;
        overflow-x: hidden;
        position: absolute;
        left: 0;
        width: 100%;
    }


</style>
