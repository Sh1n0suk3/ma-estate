<script>
    import FeatureCardSmall from './FeatureCardSmall.svelte';

    import { fly } from 'svelte/transition';
    import { onMount } from 'svelte';

    import { AOS } from 'svelte-animate-on-scroll';

    import EstateCard from './EstateCard.svelte';
    import ViewButton from './ViewButton.svelte';
    import ViewButtonBorder from './ViewButtonBorder.svelte';

    import * as consts from '$lib/constants';
    import * as feats from '$lib/features';

    let isLoaded = $state(false);

    onMount(() => {
        isLoaded = true;
    });

    let properties = $state([
		{ ...consts.ec1, visible: false },
		{ ...consts.ec2, visible: false },
		{ ...consts.ec3, visible: false }
	]);

    let features = $state([
		{ ...feats.security, visible: false },
        { ...feats.privacy, visible: false },
        { ...feats.energyEfficiency, visible: false },
        { ...feats.smartHome, visible: false },
        { ...feats.soundproofing, visible: false },
        { ...feats.heating, visible: false }
	]);

    let features1Visible = $state(false);
    let features2Visible = $state(false);

    let propertiesVisible = $state(false);
</script>

<section class="first-section" aria-labelledby="hero-heading">
    <img src="img/ecosmarta_cinematic_composited.webp" alt="a house" class="bg-image"/>
    <div class="fs-content-right">
        <div>
            <AOS animate="fade-up" ease="ease-out-cubic" delay={0} duration={1250} distance="35px">
                <h1 id="hero-heading" >Experience</h1>
            </AOS>
            <AOS animate="fade-up" ease="ease-out-cubic" delay={150} duration={1250} distance="35px">
                <h1 id="hero-heading">Ma House</h1>
            </AOS>
            <AOS animate="fade-up" ease="ease-out-cubic" delay={300} duration={1250} distance="35px">
                <ViewButtonBorder text="Properties" href="/#properties" />
                <ViewButtonBorder text="Features" href="/#features" />
            </AOS>   
        </div>
    </div>
</section>
<section class="second-section" aria-labelledby="features-heading">
    <div class="ss-content" id="properties">
        <div>
            <AOS animate="fade-up" ease="ease-out-cubic" delay={100} duration={1250} distance="35px" onupdate={(visible) => { features1Visible = true }}>
                <h2 id="features-heading">Find your home</h2>
            </AOS>
            <AOS animate="fade-up" ease="ease-out-cubic" delay={250} duration={1250} distance="35px">
                <p class="content-details">The houses that looked exactly the same and no one would even dare living in.</p>
            </AOS>
        </div>
        <div class="ma-stuff-grid">
            {#each properties as property, i (property.name)}
    				<AOS animate="fade-up" ease="ease-out-cubic" delay={50 + i * 200} duration={1250} distance="35px"><EstateCard {...property} href={`/p/${property.property}`} /></AOS>
            {/each}
        </div>
    </div>
</section>
<section class="third-section">
    <div class="ts-content" id="features">
        <AOS animate="fade-up" ease="ease-out-cubic" delay={100} duration={1250} distance="35px" onupdate={(visible) => { features2Visible = true }}>
            <h2 id="features-heading">Features</h2>
        </AOS>
        <AOS animate="fade-up" ease="ease-out-cubic" delay={250} duration={1250} distance="35px">
            <p class="content-details">Our outstanding features. A true Certified Ma Moment™</p>
        </AOS>
        <div class="ts-content-grid">
            {#each features as feature, i (feature.name)}
    	    		<AOS animate="fade-up" ease="ease-out-cubic" delay={50 + i * 200} duration={1250} distance="35px"><FeatureCardSmall {...feature} /></AOS>
            {/each}
        </div>
    </div>
</section>