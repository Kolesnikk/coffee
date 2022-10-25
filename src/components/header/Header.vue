<template>
    <header class="header">
        <div class="logo">
            <img src="@/assets/icon/logo.svg" alt="">
        </div>
        <div class="container">
            <nav>
                <ul class="left-nav">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Manu</a></li>
                    <li><a href="#">Reservation</a></li>
                </ul>
                <ul class="right-nav">
                    <li><a href="#">Pages</a></li>
                    <li><a href="#">Shop</a></li>
                    <li><a href="#">Contact</a></li>
                    <li class="burger" @click="isActive=!isActive" :class="{active: isActive}">
                        <span></span>
                        <span></span>
                        <span></span>
                    </li>
                </ul>
            </nav>
        </div>

        <div class="hamburger-menu" :class="{active: isActive}">
            <h1>Contact me</h1>
            <ul>
                <li><img src="@/assets/icon/close-outline.svg" alt=""></li>
                <li><a href=""><img src="@/assets/img/telegram.png" alt=""></a></li>
                <li><a href=""><img src="@/assets/img/telegram.png" alt=""></a></li>
                <li><a href=""><img src="@/assets/img/telegram.png" alt=""></a></li>
            </ul>
        </div>
    </header>
</template>

<script>
export default {
    name: 'header-vue',
    data() {
        return {
            isActive: false
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/variables.scss';

    .header {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        padding: 30px 0;

        .logo {
            position: absolute;
            left: 50%;
            transform: translate(-50%);
            top: 15px;
        }

        nav {
            display: flex;
            justify-content: space-between;

            ul {
                display: flex;
                li {
                    font-size: 18px;
                }
            }

            .left-nav {
                li:not(:last-child) {
                    margin-right: 50px;
                }
            }
            .right-nav {
                align-items: center;
                li {
                    &:not(:last-child) {
                        margin-right: 50px;
                    }
                }

                .burger {
                    width: 27px;
                    height: 16px;
                    position: relative;
                    margin-left: 60px;
                    cursor: pointer;

                    & span {
                        position: absolute;
                        display: block;
                        width: 100%;
                        height: 2px;
                        background: #000;

                        &:nth-child(2) {
                            top: 50%;
                            transform: translateY(-50%);
                        }
                        &:nth-child(3) {
                            bottom: 0;
                        }
                    }

                }
            }
        }

        .hamburger-menu {
            position: absolute;
            width: 40%;
            height: 60vh;
            border-bottom-left-radius: 150%;
            background: $yellow;
            top: -1000%;
            right: -100%;
            transition: .4s;   
            
            h1 {
                position: absolute;
                top: 10px;
                left: 70px;
            }
            
            &.active {
                top: 0;
                right: 0;
            }

            ul {
                position: absolute; 
                right: 10%;
                top: 25px;

                li {
                    width: 50px;
                    height: 50px;

                    &:not(:last-child) {
                        margin-bottom: 20px;
                    }

                    img {
                        width: 100%;
                    }
                }
            }
        }
    }

</style>