<script lang="ts">
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";
</script>

<div>
    <block>
        <p><header1>what is place4pals?</header1></p>
        <p>it's a non-profit, open-source, and minimalist social media platform.</p>
    </block>
    <block>
        <p><header1>who made place4pals?</header1></p>
        <p>
            chris aitken,
            <a
                style="text-decoration:underline"
                class="link"
                target="_blank"
                alt=""
                href="https://heythisischris.com/"
                >you can check out my website here</a
            >
        </p>
    </block>
</div>

<style>
    header1 {
        font-size: 24px;
        font-weight: bold;
    }
</style>
