<script lang="ts">
    import { Link } from "@inertiajs/svelte";


    let { href, children } = $props();
</script>

<Link href={ href } class="text-xl font-medium self-center underline-offset-2 hover:underline">{children}</Link>
