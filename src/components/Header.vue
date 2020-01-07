<template>
    <header id="header"> 
        <nav class="navbar">
            <ul class="navbar-col-start">
                <li id="navbar-logo" class="navbar-wrapper">
                    <img class ="navbar-item" src="/logo.png">
                </li>
                <li id="navbar-search" class="navbar-wrapper">
                    <i class="fas fa-search"></i>
                    <input class="navbar-item search" type="text" placeholder="Search ...">
                </li>
                <li class="navbar-wrapper">
                    <a href="" class="navbar-item">About</a>
                </li>
                <li class="navbar-wrapper">
                    <a href="" class="navbar-item">Explore</a>
                </li>
            </ul>

            <ul class="navbar-col-end">
                <li class="navbar-wrapper has-dropdown" @click="toggleDropdown()">
                    <i  class="navbar-item dropdown-title" id="user-icon"></i>
           
                    <div class="dropdown-content">
                        <label class="dropdown-title"> Signed as  <b>{{username}}</b></label>
                        <a class="dropdown-item" href="#"> 
                            <i class="fas fa-user"></i>
                            Dashboard 
                        </a>
                        <a class="dropdown-item" href="#"> 
                            <i class="fas fa-user"></i>
                            Profile 
                        </a>
                        <a class="dropdown-item" href="#"> 
                            <i class="fas fa-user"></i>
                            Help 
                        </a>
                        <a class="dropdown-item" href="#"> 
                            <i class="fas fa-search"></i>
                            Disconnect 
                        </a>
                    </div>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
   data() {
       return {
           username: 'louiiuol'
       }
   },
   methods: {

       toggleDropdown:  () => {
            let dropDowns = document.getElementsByClassName('has-dropdown');
            for ( let dropDown of dropDowns) {
               dropDown.children[1].classList.contains('active') ? dropDown.children[1].classList.remove('active') : dropDown.children[1].classList.add('active') 
            }

       }
       

   }
}
</script>

<style lang="scss">

    $bg: #333;

    %flex {
            display: flex; 
            flex-flow: row wrap;
            align-items: center; 
            justify-content: space-around;
            &>* { flex-grow: 1}
        }

    header#header {
    *:not(i) { font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif; }
        nav.navbar  {
            @extend %flex;
            align-items: center;
            justify-content: space-between;
            width:  100vw;
            height: 52px;
            background: $bg;
            color:  #AAA;
            padding: 0 4vw 0 1vw;
            position: relative;
            ul[class*="navbar-col"] { 
                @extend %flex;
                height: 48px;
                li { list-style: none;}
                a {text-decoration: none; color: currentColor;}

                &[class*="start"] {
                    max-width: 50vw;
                    justify-self: start;
                    justify-content: flex-start;
                    * { flex-grow: 0;}
                    li.navbar-wrapper {
                        margin-left: 2rem;
                        i.fas { font-size: 20pt; margin-right: .85rem;}
                        &#navbar-search:hover input.search{ max-width: 20vw;}
                        input.search  {
                            height: 42px;
                            width: 200px;
                            background: #fff;
                            color: currentColor;
                            font: inherit;
                            box-shadow: 0 6px 10px 0 rgba(0, 0, 0 , .1);
                            border: 0;
                            outline: 0;
                            max-width: 0;
                            transition: max-width .6s cubic-bezier(0.165, 0.84, 0.44, 1)
                        }
                    }
                    li#navbar-logo {
                        @extend %flex;
                        img {
                            max-height: 36px;
                            max-width: 75px; 
                        }
                    }
                }
                &[class*="end"] {
                    flex-grow: 0;
                    justify-self: end;
                    justify-content: flex-end;
                }
                li.navbar-wrapper {
                    @extend %flex;
                    height: 48px;
                    &.has-dropdown {
                        @extend %flex;
                        flex-grow: 0;
                       justify-content: flex-end;
                        position: relative;
                        max-height: 48px;
                        * { align-items: stretch; }
                        &::after {
                            content:'';
                            position: absolute;
                            top: 24%;
                            right: 0;
                            width: 0;
                            height: 0;
                            border-top: solid 20px currentColor;
                            border-left: solid 10px transparent;
                            border-right: solid 10px transparent;
                        }
                        i#user-icon {
                                width: 42px;
                                height: 42px;
                                border-radius: 50%; 
                                background: #AAA;
                                flex-grow: 0;
                                margin-right: 30px;
                        }
                        label.dropdown-title {
                            border-bottom: 2px solid currentColor;
                        }
                        .dropdown-content{
                            @extend %flex;
                            background: white;
                            flex-direction: column;
                            transition: max-height .6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
                            box-shadow: 0 4px 8px rgba(0,0,0,.15);
                            border-radius: 2px;
                            position: absolute;
                            top: 150%;
                            right: -1rem;
                            .dropdown-title {
                                padding: .85rem 0;
                                font-size: 10pt;
                                font-weight: bolder;
                            }
                            .dropdown-item{
                                @extend %flex;
                                justify-content: flex-start;
                                width: 150px;
                                padding: 1rem 0;
                                border-bottom: 1px solid currentColor;
                                * { flex-grow: 0; margin-left: 1rem; margin-right: .5rem;}
                                &:hover { background: #999; color: #222}
                            }
                            &.active { max-height: 300px; }
                        }
                    }
                }
            }
        }
    }
    
        
        
</style>