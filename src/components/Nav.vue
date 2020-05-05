<template>
    <div id="navbar">
        <header class="z-depth-2" :class="darkMode ? 'darkMode' : 'whiteMode'">
            <button data-target="slide-out" class="sidenav-trigger">
                <i class="material-icons">menu</i>
            </button>
            <h1>Skin</h1>
            <div class="switch">
                <label @change="$emit('mode')">
                    <i class="material-icons sol">wb_sunny</i>
                    <input type="checkbox">
                    <span class="lever"></span>
                    <i class="material-icons luna">brightness_3</i>
                </label>
            </div>
        </header>
        <ul id="slide-out" class="sidenav" :class="darkMode ? 'darkMode' : 'whiteMode'">
            <li>
                <span class="icon-person"><i class="material-icons">person</i></span>
                <div class="user-view">
                    <span class="name">Chaapu</span>
                    <span class="email">ezequiel.guardia@davinci.edu.ar</span>
                </div>
            </li>
            <li><a class="waves-effect routes" href="#">Iniciar Sesión</a></li>
            <li><a class="waves-effect routes" href="#">Registrarse</a></li>
        </ul>


    </div>
</template>

<script>
export default {
  name: 'navbar',
  props:['darkMode'],

  mounted() {
    $(document).ready(function(){
        $('.sidenav').sidenav();
        $('.dropdown-trigger').dropdown({
            'constrainWidth': false,
            'coverTrigger': false,
            
        });
    });
  },
  
  methods: {
    closeNav(){
        let instance = M.Sidenav.getInstance(document.querySelector('.sidenav'));
        instance.close();
    },
  },
  
}
</script>

<style scoped>
    .darkMode{
        background: #292d3e;
        color: white;
        transition: background .2s linear;
    }

    .whiteMode{
        background: white;
        color: black;
        transition: background .2s linear;
    }

    /*----HEADER----*/
    header{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 10px;
    }

    header.whiteMode{
        border-bottom: 1px solid rgba(0, 0, 0, .2);
    }

    header.darkMode{
        border-bottom: 1px solid white;
    }

    header h1{
        margin: 0;
        font-size: 32px;
        font-weight: bolder;
    }

    header button{
        background: transparent;
        border: 0;
        outline: 0;
        cursor: pointer;
        font-size: 24px;
    }

    header.whiteMode button{
        color: black;
    }

    header.darkMode button{
        color: white;
    }

    header .switch label{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    header .switch label .lever{
        margin: 0 5px;
    }

    .switch label input[type="checkbox"]:checked + .lever::after {
        background-color: white;
    }

    header.darkMode .switch label input[type="checkbox"]:checked + .lever {
        background-color: rgba(255,255,255,0.38);;
    }

    header .luna, header .sol{
        font-size: 18px;
    }

    header.darkMode .sol{
        color: yellow;
    }

    header.darkMode .luna{
        color: white;
    }


    /*----SIDENAV----*/

    .darkMode .routes{
        color: white;
        font-weight: bolder;

    }

    .whiteMode .routes{
        color: black;
        font-weight: bolder;

    }

    .routes:hover{
        color: #9c2222;
    }

    .darkMode .user-view{
        border-bottom: 1px solid rgba(255, 255, 255, .4);
    }

    .whiteMode .user-view{
        border-bottom: 1px solid rgba(0, 0, 0, .4);
    }

    .user-view{
        text-align: left;
        padding-top: 0;
    }

    .user-view .name{
        font-weight: bolder;
        margin-top: 0;
    }
    .icon-person .material-icons{
        font-size: 40px;
        margin-top: 25px;
    }

    

    #login{
        font-size: 14px;
    }

    #login a{
        font-size: 14px;
        font-weight: bolder;
        color: black;
    }

    #login.darkMode a{
        color: white;
    }

    #login.darkMode li:hover{
        background: rgba(255, 255, 255, .3);
    }

    #login.whiteMode li:hover{
        background: rgba(0, 0, 0, .1);
    }
</style>