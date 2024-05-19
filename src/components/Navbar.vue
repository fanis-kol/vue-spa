<template>
    <nav 
        :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar navbar-expand']"
    >
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                   <navbar-link
                        :page="page"
                        :is-active="activePage === index"
                        @click.prevent="navLinkClick(index)"
                    ></navbar-link>
                </li>
            </ul>
            <form class="d-flex">
                <button 
                    class="btn btn-primary"
                    @click.prevent="changeTheme()"
                >Toggle Navbar
                </button>
            </form>
        </div>
    </nav>

</template>


<script>

import  NavbarLink from './NavbarLink.vue';
export default{

    components : {
        NavbarLink
    },

props:['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'Light',
        }
    },
    methods:{
        changeTheme(){
            let theme = 'Light';

            if(this.theme == 'Light'){
                theme = 'dark';
            }

            this.theme = theme;
        }
    }
}


</script>
