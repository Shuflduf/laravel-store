<script lang="ts">
    import { Link, page } from "@inertiajs/svelte";
    import Button from "../ui/button/button.svelte";
    import StyledLink from "./StyledLink.svelte";
    import { onMount } from "svelte";
    import { User } from '@geist-ui/icons';

    onMount(() => {
        let user = $page.props.auth.user;
        console.log(user.name)
    });
</script>

<div class="flex justify-between fixed top-0 w-screen border-b-zinc-600 border-b-1 bg-zinc-800/50 backdrop-blur-md">
    <p class="w-1/4 text-2xl self-center mx-4">Logo Design</p>
    <div class="flex gap-6 m-2 justify-center w-1/2">
        <StyledLink href={route('testing')} children="Home" />
        <StyledLink href={route('testing')} children="Shop" />
    </div>
    <div class="flex gap-4 m-2 justify-end w-1/4">
        {#if $page.props.auth.user}
            <Link href={route('dashboard')} >
                <Button class="flex gap-2">
                    <User />
                    {$page.props.auth.user.name}
                </Button>
            </Link>
        {:else}
            <Link href={route('login')} >
                <Button variant="primary">Login</Button>
            </Link>
        {/if}
    </div>
</div>
