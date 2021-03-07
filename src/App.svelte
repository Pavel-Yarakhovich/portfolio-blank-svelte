<script>
	import Header from "./Components/Header.svelte";
	import Footer from "./Components/Footer.svelte";
	import About from "./Components/About.svelte";
	import Resume from "./Components/Resume.svelte";
	import Contact from "./Components/Contact.svelte";
	import Testimonials from "./Components/Testimonials.svelte";
	import Portfolio from "./Components/Portfolio.svelte";
	
	const fetchData = (async () => {
		const response = await fetch("resumeData.json");
		return await response.json();
	})();
</script>

<style>
	div {
		width: 100%;
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	p {
		color: white;
	}
</style>

<div>
	{#await fetchData}
		<p>Loader...</p>
	{:then data}
		<Header data={data.main} />
		<About data={data.main} />
		<Resume data={data.resume} />
		<Portfolio data={data.portfolio} />
		<Testimonials data={data.testimonials} />
		<Contact data={data.main} />
		<Footer data={data.main} />
	{:catch error}
		<p>An error occured: {error}</p>
	{/await}
</div>
