<script>
    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte";
    // import Promise from "$lib/components/Promise.svelte";

    export let data
    // console.log(data.promisePages)
</script>

<Header />

<main>

    {#each data.promisePages as promisePage }
    
        <h1>{promisePage.promiseIntro.title}</h1>
        
        <div class="block-text-2">
            <section class="block-text" >
            <!-- <div class="block"> -->
                    <p class="text1"> {promisePage.promiseIntro.contentText}</p>
                    <p class="text2"> {promisePage.promiseIntro.contentText2}</p>
            <!-- </div> -->
            </section>
        </div>
        <img src="{promisePage.promiseIntro.contentImg.url}" alt="content" class="img">

    {/each}


    {#each data.promisePages as promisePage }

        <div class="block-text-2">
            <h2>{promisePage.promiseMain.title}</h2>
            <p class="text3"> {promisePage.promiseMain.contentText}</p>
        </div>
    
    {/each}


<!-- <Promise {data}/> -->

</main>

<Footer />

<style>


    /*mobile first*/
    h1{
        font-size: 2em;
        padding: 3em;
    }

    h2{
        font-size: 2em;;
        padding:1em;
        max-width:30em;
    }

    .text1, .text2{
        padding: 1em 1em;
        font-size: 1em;
        max-width: 30em;
        align-items: center;
    }

    .text3{
        padding: 2em 2em;
        font-size: 1em;
        max-width: 30em;
        align-items: center;
    }

    section{
        display:grid;
        grid-template-rows:auto 8em auto;
        grid-row-start:1;
        grid-row-end:3;
        grid-column-start:1;
        background-color: var(--jungleGreen);
        clip-path:
            polygon(
                0% 4em,
                30% 0,
                100% 4.5em,
                100% calc(100% - 2em),
                0% 100%,
                0% 4em
            );
        z-index:10;
        margin:0;
        padding:5em 3em;
    }

    .img{
    max-width:100%;
    width:100%;
	grid-row-start:2;
	grid-row-end:4;
	grid-column-start:1;
    clip-path:
		polygon(
			0% 10%,
			100% 0%,
			100% 30%,
			100% 100%,
			20% 100%,
			0% 100%
        );
    }

    .block-text-2 {
        background-image: url("/Subtract.png");
        width:100%;
        height:-50%;
        /* opacity: .5; */
        object-fit: contain;
    }


    @media only screen and (min-width: 768px) and (max-width: 1200px) {

        .text1, .text2, .text3{
            margin: 0 auto;
            font-size: 1em;
        }

        h1{
            margin: 0 auto;
            align-items:center;
        }

        h2{
            margin: 0 auto;
            align-items:center;
        }

        .block-text-2{
            padding-bottom: 50px;
                padding-top:30px;
        }
    }

</style>