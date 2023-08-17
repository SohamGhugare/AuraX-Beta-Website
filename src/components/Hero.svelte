<script>
    import { onMount, onDestroy } from "svelte";
    import { slide } from "svelte/transition";

    let texts = ["of Business", "in AR/VR"];
    let index=0;
    // @ts-ignore
    let roller;

    onMount(() => {
        roller = setInterval(() => {
            if(index == texts.length-1) index=0;
            else index++;
        }, 1250);
    });

    onDestroy(() => {
		// @ts-ignore
		clearInterval(roller);
	});

</script>

<div class="hero">
    <div class="hero-text">
        Building the Future
    </div>
    <div class="rolling-text" >
        {#key index}
            <h1 transition:slide>{texts[index]}</h1>
        {/key}
    </div>
    <div class="coming-soon">
        Coming Soon..!
    </div>
</div>

<footer class="footer">
    &copy; 2023 AuraX Technovations
</footer>


<style>
    .hero {
        display: flex;
        flex-direction: column;
        padding-top: 150px;
        margin-right: 0;
    }
    .hero-text {
        display: flex;
        font-size: 5rem;
        font-family: Outfit;
        align-items: center;
        justify-content: center;
    }

    .rolling-text {
        display: flex;
        flex-direction: column;
        font-family: Outfit;
        font-size: 2rem;
        color: #14C9B4;
        align-items: center;
        justify-content: center;
    }
    .coming-soon {
        display: flex;
        font-size: 2rem;
        font-family: Outfit;
        align-items: center;
        justify-content: center;

    }

    .footer {
        text-align: center;
        font-family: Outfit;
        color: white;
        padding: 10px;
        position: absolute;
        bottom: 0;
        width: 100%;
    }
</style>