<script lang="ts">
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";
</script>

<div>
    <div style="text-align:center;margin-top:10vh;margin-bottom:-5vh;">
        <block>
            <p><header1>what is place4pals?</header1></p>
            <p>
                it's a minimalist, non-profit, and open-source social media
                platform.
            </p>
        </block>
        <block>
            <p><header1>who made place4pals?</header1></p>
            <p>
                chris aitken, you can check out his website and other projects
                <a
                    style="text-decoration:underline"
                    class="link"
                    target="_blank"
                    alt=""
                    href="https://heythisischris.com">here</a
                >.
            </p>
        </block>

        <block>
            <p><header1>how can i help place4pals?</header1></p>
            <p>
                shoot us an email! <a
                    style="text-decoration:underline"
                    class="link"
                    target="_blank"
                    alt=""
                    href="mailto:support@place4pals.com"
                    >support@place4pals.com</a
                >.
            </p>
        </block>
    </div>
</div>

<style>
    header1 {
        font-size: 24px;
        font-weight: bold;
    }
</style>
