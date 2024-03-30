<template>
    <nav 
        :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar navbar-expand']"
    >
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">

                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <a class="nav-link"
                    :class="{active: activePage == index}"
                    aria-current="page" 
                    :href="page.link.url" 
                    :title="`This link Goes to the ${page.link.text} Page`"
                    @click.prevent="navLinkClick(index)"
                    >
                    {{ page.link.text }}
                    </a>
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

export default{

props:['pages', 'activePage', 'navLinkClick'],
    data() {
        return {
            theme: 'light',
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
