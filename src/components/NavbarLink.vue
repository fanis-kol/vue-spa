<template>
       <a   
            class="nav-link"
            :class="activeClasses"
            aria-current="page" 
            :href="page.link.url" 
            :title="`This link Goes to the ${page.link.text} Page`"
            >
            {{ page.link.text }}
        </a>
</template>

<script>
export default {
    props: ['page', 'isActive'],
    computed : {
        activeClasses(){
            return {
                active: this.isActive,
                emphasize: this.isActive
            }
        }
    }
}

</script>

<style>
.emphasize{
    text-decoration: underline !important;
}

</style>