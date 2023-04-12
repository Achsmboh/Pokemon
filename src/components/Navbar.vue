<template>
    <nav>
        <div class="dropdown">
            <div class="hamburger"  @click="toggleMenu()" :class="{actvhum:isOpen}"> 
                <span></span>
                <span></span>
                <span></span>
            </div>
            
            <div class="profile">
                <img src="https://assets.pokemon.com/static2/_ui/img/chrome/profile-navigation/profile-nav-signup.png" alt="profile">
                <p>Log In</p>
            </div>
        </div>
        <div class="nav-menu" :class="{show:isOpen}">
            <a  href="#home" class="card-menu nav-home" @click="active('.nav-home')" >
                <img class="icon-white" src="../assets/home.svg" alt="home">
                <img class="icon-abu" src="../assets/home-abu.svg" alt="home">
                <p>Home</p>
            </a>
            <a href="#pokedex" class="card-menu nav-pokedex" @click="active('.nav-pokedex')" >
                <img class="icon-abu" src="../assets/pokemon-abu.svg" alt="pokemon">
                <img class="icon-white"  src="../assets/pokemon.svg" alt="pokemon">
                <p>Pokédex</p>
            </a>
            <a href="#video" class="card-menu nav-video"  @click="active('.nav-video')">
                <img class="icon-abu" src="../assets/game-abu.svg" alt="game">
                <img class="icon-white"  src="../assets/game.svg" alt="game">
                <p>Video games 	&amp; Apps</p>
            </a>
            <a href="#tradding" class="card-menu nav-tradding menu-drop"  @click="active('.nav-tradding')">
                <div class="icon-menu">
                    <img class="icon-abu" src="../assets/card-abu.svg" alt="card">
                    <img class="icon-white" src="../assets/card.svg" alt="card">
                    <p>Tradding Card Game</p>
                </div>
                <div class="arrow">
                    &rsaquo;
                </div>
                
            </a>
            <a href="#tv" class="card-menu nav-tv"  @click="active('.nav-tv')">
                <img class="icon-abu" src="../assets/tv-abu.svg" alt="tv">
                <img class="icon-white" src="../assets/tv.svg" alt="tv">
                <p>Pokémon TV</p>
            </a>
            <a href="#event" class="card-menu nav-event menu-drop"  @click="active('.nav-event')">
                
                <div class="icon-menu">
                    <img class="icon-abu" src="../assets/event-abu.svg" alt="event">
                    <img class="icon-white" src="../assets/event.svg" alt="event">
                    <p>Play! Pokémon Events</p>
                </div>
                <div class="arrow">
                    &rsaquo;
                </div>
            </a>
            <a href="#news" class="card-menu nav-news"  @click="active('.nav-news')">
                <img class="icon-abu" src="../assets/news-abu.svg" alt="news">
                <img class="icon-white" src="../assets/news.svg" alt="news">
                <p>News</p>
            </a>
        </div>
    </nav>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'NavbarMenu',
    data() {
    return {
      isOpen: true,
    };
    },
    methods: {
        toggleMenu() {
             this.isOpen = !this.isOpen;
    },
        active(nav: string) {
      // Ambil semua elemen navbar
      const navItems = document.querySelectorAll('.card-menu');
      // Loop semua elemen navbar dan hapus kelas "active"
      navItems.forEach((item) => {
        item.classList.remove('active');
      });
      // Tambahkan kelas "active" ke elemen yang baru saja di-klik
      const clickedNavItem = document.querySelector(nav);
      clickedNavItem?.classList.add('active');
    },
    },   
});
</script>
<style scoped>



@media screen and (min-width: 960px) {
    .card-menu p{
    font-size: 14px;
    margin-top: 4px;
    }
    .arrow{
        display: none;
    }
    .dropdown{
        display: none;
    }
    nav{
        color: white;
        margin: 0;
        padding: 0;
        background: white;
        height: 87px;
        display: flex;
        justify-content: center;
        align-items: center;
        box-shadow: 3px 0 2px 0 black;
        font-family: 'Roboto', sans-serif;
    }
    h1, p{
        margin: 0;
    }
    .nav-menu{
        height: 100%;
        width: 894px;
        display: flex;
    }
    .card-menu{
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: start;
        align-items: center;
        flex-direction: column;
        color: #46494c;
        cursor: pointer;
    }
    
    img.icon-white{
        display: none;
    }
    .card-menu:hover img.icon-white, .card-menu.active img.icon-white{
        display: inline-block;
      }
    .card-menu:hover img.icon-abu, .card-menu.active img.icon-abu{
        display: none;
    }

    .card-menu img{
        width: 30px;
        padding-top: 10px;
        color: #464645;
    }
    .nav-home{
        border-bottom: 5px solid #919191;
        border-radius: 0 0 0 5px;
    }
    .nav-home:hover, .nav-home.active{
        background: #919191;
        color: white;
    }
    
    .nav-pokedex{
        border-bottom: 5px solid #e3350d;
        border-radius: 0 0 0 0;
    }
    .nav-pokedex:hover, .nav-pokedex.active{
        background: #e3350d;
        color: white;
    }
    .nav-video{
        border-bottom: 5px solid #ee6b2f;
    }
    .nav-video:hover, .nav-video.active{
        background: #ee6b2f;
        color: white;
    }
    .nav-tradding{
        border-bottom: 5px solid #e6bc2f;
    }
    .nav-tradding:hover, .nav-tradding.active{
        background: #e6bc2f;
        color: white;
    }
    .nav-tv{
        border-bottom: 5px solid #4dad5b;
    }
    .nav-tv:hover, .nav-tv.active{
        background: #4dad5b;
        color: white;
    }
    .nav-event{
        border-bottom: 5px solid #30a7d7;
    }
    .nav-event:hover, .nav-event.active{
        background: #30a7d7;
        color: white;
    }
    .nav-news{
        border-bottom: 5px solid #1b53ba;
    }
    .nav-news:hover, .nav-news.active{
        background: #1b53ba;
        color: white;
    }
}

a{
    text-decoration: none;
    color: #46494c;
}

@media screen and (max-width: 959px) {
    .nav-menu {
        display: none;
      }
      .show{
        display: block;
      } 
    div.actvhum{
        background: black;
    }
    div.actvhum span {
        background: #46494c;
    }
    .show.active .hamburger{
     background: red;
    }
      .dropdown.active .nav-menu {
        display: block;
      }
    nav{
        background: radial-gradient(#464645, rgb(26, 25, 25),rgb(26, 25, 25)); 
        height: 58px;
        width: 100%;
    }
    .card-menu img.icon-white{
        display: none;
    }
    a.menu-drop{
        display: flex;
        justify-content: space-between;
        width: 100%;
    }
    .icon-menu{
        display: flex;
        align-items: center;
    }
    .arrow{
        width: 55px;
        height: 55px;
        background: #c3c3c3;
        color: white;
        font-size: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 0;
    }

    .dropdown{
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 100%;
    }
    .nav-menu{
        top: 58px;
        left: 0;
        position: absolute;
        height: 385px;
        width: 100%;
    }
    .card-menu img{
        width: 30px;
        height: 30px;
        margin: 0 25px;
    }
    .card-menu{
        display: flex;
        align-items: center;
        border-bottom: 1px solid #c3c3c3;
        width: 100%;
    }
    .hamburger span {
        width: 23px;
        height: 4px;
        background: white;
    }
    .hamburger{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background:#313131 ;
        gap: 3px;
        height: 100%;
        width: 59px;
    }
    .profile{
        background:#313131 ;
        height: 100%;
        width: 49px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: white;
    }
    .profile img{
        height: 38px;
    }
    .profile p{
        margin: 0;
        font-size: 9px;
    }
    .nav-home{
        border-left: 7px solid #919191;
    }
    .nav-pokedex{
        border-left: 7px solid #e3350d;
    }
    .nav-video{
        border-left: 7px solid #ee6b2f;
    }
    .nav-tradding{
        border-left: 7px solid #e6bc2f;
    }
    .nav-tv{
        border-left: 7px solid #4dad5b;
    }
    .nav-event{
        border-left: 7px solid #30a7d7;
    }
    .nav-news{
        border-left: 7px solid #1b53ba;
    }
}
</style>