<script>
    import { active } from "tinro";
</script>

<style>
    :global(.active) {
        font-weight: bold;
        text-decoration: underline;
    }
    a {
        outline: none;
    }
</style>

<nav>
    <a href="/" use:active exact>Dashboard</a>
    <a href="/profile" use:active>Profile</a>
</nav>
