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
        <router-link to="/About">O mne</router-link>
        <router-link to="/Skills">Kariera</router-link>
        <router-link to="/FreeTime">Hobby</router-link>
      </div>

      <div class="media">
        <a href="https://www.instagram.com/velky_simi/?hl=sk" target="_blank" rel="noopener noreferrer">
        <ion-icon name="logo-instagram"></ion-icon>
        </a>
        <a href="https://github.com/xSimekj1" target="_blank" rel="noopener noreferrer">
          <ion-icon name="logo-github"></ion-icon>
        </a>
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
    z-index: 2;
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
      transition: 0.4s;
      &:hover {
        color: @cyan;
      }
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
    width: 100%;
    display: flex;
    flex-direction: column;
    margin-top: 50px;
    a {
      font-weight: bold;
      padding: 20px 0;
      border-bottom: 1px solid;
      &:nth-of-type(1) {
        border-top: 1px solid;
      }
    }
  }

  .media {
    position: absolute;
    width: 160px;
    display: flex;
    justify-content: space-around;
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
