<template>
    <div>
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <a class="navbar-brand" href="#">Laravel</a>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto" :class="(link in linksHeader)">
                <li class="nav-item">
                    <a class="nav-link" href="#">link.lable<span class="sr-only"></span></a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">link.lable</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">link.lable</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">link.lable</a>
                </li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name:"Header",
    data(){
        return{
            linksHeader:[
                {
                    lable:'Home',
                    link:'#'
                },
                {
                    lable:'Home',
                    link:'#'
                },
                {
                    lable:'Home',
                    link:'#'
                },
                {
                    lable:'Home',
                    link:'#'
                }
            ]
        }
    }
}
</script>

<style>

</style>