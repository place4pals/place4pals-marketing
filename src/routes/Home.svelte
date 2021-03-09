<script lang="ts">
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";
    import { writable } from "svelte/store";
    const loaded = writable(sessionStorage.getItem("loaded") || "");
    loaded.subscribe((val) => sessionStorage.setItem("loaded", val));
    //loaded.set(0);
    onMount(() => {
        loaded.set(1);
    });
    const delaysConfig = [500, 1500, 2500, 3500];
    let delays = [];
    for (let i = 0; i < delaysConfig.length; i++) {
        if (!$loaded) {
            delays[i] = { delay: delaysConfig[i], duration: 500 };
        } else {
            delays[i] = { delay: 0, duration: 0 };
        }
    }
    setTimeout(() => {
        let scroll = document.getElementById("scroll");
        function scrollFunction() {
            setTimeout(() => {
                if (scroll.scrollTop === scroll.scrollHeight - 500) {
                    scroll.scrollTo({
                        top: 0,
                        left: 0,
                        behavior: "auto",
                    });
                    scrollFunction();
                } else {
                    scroll.scrollBy({
                        top: 3,
                        left: 0,
                        behavior: "smooth",
                    });
                    scrollFunction();
                }
            }, 35);
        }
        scrollFunction();
    }, 0);
</script>

<div>
    <p in:fade={delays[0]} style="text-align:center;">
        non-profit <span in:fade={delays[1]}>and open-source </span><span
            in:fade={delays[2]}
        >
            social media</span
        >
    </p>
    <div id="scrollContainer" in:fade={delays[3]}>
        <div id="scroll" in:fade={delays[3]}>
            <img alt="" class="image" src="feed.jpg" />
        </div>
    </div>
    <div in:fade={delays[3]}>
        <p><header1>news</header1></p>
        <p>
            03/08/2021 @ 7:30pm est - launched the marketing website for
            place4pals
        </p>
    </div>
</div>

<style>
    header1 {
        font-size: 30px;
        font-weight: bold;
    }
    #scroll {
        height: 500px;
        overflow-y: hidden;
        overflow-x: hidden;
    }
    #scrollContainer {
    }
</style>
