<template>
    <div>
        <nav>
            <ul>
                <li><a href="">Home</a></li>
                <li><a href="">Post</a></li>
                <li><a href="">About</a></li>
                <li><a href="">Contact</a></li>
            </ul>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Navbar',
    data() {
        return {

        }
    }
}
</script>

<style>
    nav li {
        display: inline-block;
        margin: 5px;
    }
</style>