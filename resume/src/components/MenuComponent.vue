<template>
  <div class="menu">
      <div class="profile">
        <div class="image-holder">
          <img src="@/assets/images/avatar.png">
        </div>
        <h1>Jakub Šimek</h1>
        <div class="contact">
          <span>
            <ion-icon name="mail-outline"></ion-icon>
            Jakapo.simek95@gmail.com
          </span>
          <span>
            <ion-icon name="call-outline"></ion-icon>
            +421 917 174 171
          </span>
        </div>
      </div>

      <div class="nav">
        <router-link to="/Home">O mne</router-link>
        <router-link to="/about">Kariera</router-link>
        <router-link to="/">Hobby</router-link>
      </div>

      <div class="media">
        <ion-icon name="logo-facebook"></ion-icon>
        <ion-icon name="logo-instagram"></ion-icon>
        <ion-icon name="logo-github"></ion-icon>
      </div>

      <span class="trademark">
        @Šimi.osobne <br>
        Powered by Vue.js
      </span>

  </div>
</template>

<script>
export default {
  name: 'MenuComponent',
};
</script>

<style lang="less">
@import './../assets/styles/global.less';

  .menu {
    position: fixed;
    top: 0;
    display: flex;
    flex-direction: column;
    height: 100vh;
    width: 300px;
    align-items: center;
    text-align: center;
    color: @grayish-violet;
    background-color: @dark-violet;
    box-shadow: 1px 0px 5px 0px rgba(140,140,140,1);
    a {
      color: @grayish-violet;
    }
  }

</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  .profile {
    margin-top: 40px;
    .image-holder {
      img {
        width: 250px;
      }
    }
    h1 {
      margin: 15px 0;
    }
    .contact {
      display: flex;
      flex-direction: column;
      span {
        display: flex;
        flex-direction: row;
        margin-top: 10px;
        ion-icon {
          margin-right: 15px;
        }
      }
    }
  }
  .nav {
    display: flex;
    flex-direction: column;
    margin-top: 50px;
    a {
      margin: 10px 0;
    }
  }

  .media {
    position: absolute;
    width: 160px;
    display: flex;
    justify-content: space-between;
    bottom: 70px;
    ion-icon {
      font-size: 36px;
    }
  }

  .trademark {
    position: absolute;
    bottom: 10px;
    font-size: 14px;
  }

</style>
