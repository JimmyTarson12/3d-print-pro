<script lang="ts">
    import { onMount } from "svelte";
    import { animate } from "motion"

    var animatedTitle: HTMLElement

    const heroWords: string[] = ["Easy", "Simple", "Affordable", "Effortless", "Accessible", "Convenient", "Reliable", "Seamless", "Intuitive"]
    let currentWordIndex: number = 0

    let titleAnimationIsDone: boolean = false
    onMount(() => {
        setTimeout(() => {
            startHeroAnimation()
        }, 3000)
    })

    function startHeroAnimation() {
        const heroAnimationOut = animate(animatedTitle, { transform: "translateX(170px)", opacity: 0, }, {
            duration: 0.8,
        })
        heroAnimationOut.finished.then(() => {
            resetHeroAnimation(animatedTitle).then(() => {
                titleAnimationIsDone = true
            })
        })
    }

    $: if (titleAnimationIsDone == true) {
        titleAnimationIsDone = false
        currentWordIndex++
        if (currentWordIndex >= heroWords.length) currentWordIndex = 0
        const animation = animate(animatedTitle, { transform: "translateX(0px)", opacity: 1, }, {
            duration: 0.8,
            onComplete: () => {
                setTimeout(() => {
                    startHeroAnimation()
                }, 3000)
            }
        })
    }

    function resetHeroAnimation(element: HTMLElement) {
        return animate(element, { transform: "translateX(-170px)", }, {duration: 0,}).finished
    }
</script>

<section class="py-12 bg-black sm:pb-16 lg:pb-20 xl:pb-24">
	<div class="px-4 mx-auto sm:px-6 lg:px-8 max-w-7xl">
		<div class="relative">
			<div class="lg:w-2/3">
				<p class="text-sm font-normal tracking-widest text-gray-300 uppercase">A Hub for Creativity, Design & Creation</p>
				<h1 class="mt-6 text-4xl font-normal text-white sm:mt-10 sm:text-5xl lg:text-6xl xl:text-8xl">
					<span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-500 to-purple-500">Printing Made<br></span><span bind:this={animatedTitle} class="inline-block">{heroWords[currentWordIndex]}</span>
				</h1>
				<p class="max-w-lg mt-4 text-xl font-normal text-gray-400 sm:mt-8">
					3D printing doesn't have to be complicated. Our platform guides you through every step so you can spend less time figuring things out, and more time creating.
				</p>

				<div class="relative inline-flex items-center justify-center mt-8 sm:mt-12 group">
					<div class="absolute transition-all duration-200 rounded-full -inset-px bg-gradient-to-r from-cyan-500 to-purple-500 group-hover:shadow-lg group-hover:shadow-cyan-500/50"></div>
					<a href="/home" class="relative inline-flex items-center justify-center px-8 py-3 text-base font-normal text-white bg-black border border-transparent rounded-full">Start Creating Today</a>
				</div>
			</div>

			<div class="mt-8 md:absolute md:mt-0 md:top-32 lg:top-0 md:right-0">
				<!-- svelte-ignore a11y_img_redundant_alt -->
				<img class="w-full max-w-xs mx-auto lg:max-w-lg xl:max-w-xl" src="https://landingfoliocom.imgix.net/store/collection/dusk/images/hero/1/3d-illustration.png" alt="Hero Image" />
			</div>
		</div>
	</div>
</section>
