<template>
  <div class="skills">
    <img class="background" src="@/assets/images/skills.jpg">
    <div class="content-grid">
      <div
      v-for="tile in tiles" :key="tile.name"
      class="tile"
      v-bind:class="[
        { 'content-detail': tile.name === 'detail'},
        getColor(tile),
        isActive(tile.name)
      ]"
      >
        <div class="detail-content" v-if="tile.name === 'detail'">
          <div class="detail-title">Šimiho skillset</div>
          <div class="col">
            <div class="row">
              <div class="label">Typ:</div>
              <div class="description">
                <transition name="slide-fade" mode="out-in">
                  <span v-if="activeTile" :key="activeTile.type">
                    {{activeTile.type}}
                  </span>
                </transition>
              </div>
            </div>
            <div class="row">
              <div class="label">Prax:</div>
              <div class="description">
                <transition name="slide-fade" mode="out-in">
                  <span v-if="activeTile" :key="activeTile.experience">
                    {{activeTile.experience}}
                  </span>
                </transition>
              </div>
            </div>
            <div class="row">
              <div class="label">Popis:</div>
              <div class="description">
                <transition name="slide-fade" mode="out-in">
                  <span v-if="activeTile" :key="activeTile.description">
                    {{activeTile.description}}
                  </span>
                </transition>
              </div>
            </div>
          </div>
        </div>
        <div class="tile-content" @click="setActive(tile)" v-else>
          <span class="tile-image">
            <img :src="require(`@/assets/logo/` + tile.image)">
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Skills',
  data: () => ({
    activeTile: null,
    tiles: [
      {
        name: 'Angular',
        experience: '1 rok',
        type: 'JS framework',
        description: 'Angular 7+, tvorba inzerčných portálov, objednávkových systémov, poisťovacích systémov.',
        image: 'angular.png',
        color: 'red',
      },
      {
        name: 'Vue',
        experience: 'menej ako 1 rok',
        type: 'JS framework',
        description: 'Tvorba jednoduchších SPA v rámci školských a súkromných projektov',
        image: 'vue.png',
        color: 'cyan',
      },
      {
        name: 'Bootstrap',
        experience: '1 rok',
        type: 'CSS framework',
        description: 'Tvorba komerčných projektov, práca s templatami',
        image: 'bootstrap.png',
        color: 'purple',
      },
      {
        name: 'HTML-5',
        experience: '3 roky',
        type: 'Technológia',
        description: '',
        image: 'html.png',
        color: 'red',
      },
      {
        name: 'detail',
      },
      {
        name: 'CSS3',
        experience: '3 roky',
        type: 'Technológia',
        description: 'Responzívny dizajn, práca s preprocesormi SCSS, LESS',
        image: 'css.png',
        color: 'blue',
      },
      {
        name: 'Javascript',
        experience: '3 roky',
        type: 'Technológia',
        description: '',
        image: 'javascript.png',
        color: 'yellow',
      },
      {
        name: 'Github',
        experience: '2 roky',
        type: 'Verziovací nástroj',
        description: 'Základný manažment a práca s branchami z pozície zamestnanca.',
        image: 'github.svg',
        color: 'black',
      },
      {
        name: 'Firebase',
        experience: '1 rok',
        type: 'Backend as a service',
        description: 'Práca s databázou a prihlasovaním na súkromných projektoch',
        image: 'firebase.png',
        color: 'yellow',
      },
    ],
  }),
  methods: {
    getColor(tile) {
      return tile.color;
    },
    setActive(tile) {
      this.activeTile = tile;
    },
    isActive(tileName) {
      if (this.activeTile) {
        return tileName === this.activeTile.name ? 'active' : '';
      }
      return '';
    },
    setClass(tile) {
      if (tile.name === 'detail') {
        return 'content-detail';
      }
      return 'content';
    },
  },
};
</script>

<style lang="less">
@import './../assets/styles/global.less';

.skills {
  position: relative;
  overflow: hidden;
  background: @gray;
  height: 100vh;
  padding-left: 300px;
  .background {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: auto;
    opacity: 0.2;
  }
  .content-grid {
    display: grid;
    height: 100vh;
    grid-template-columns: repeat(3, 1fr);
    grid-template-areas: ". . ." ". . ." ". . .";
    .tile {
      z-index: 2;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transition: 0.4s;
      &.content-detail {
        &:hover {
          background: unset !important;
        }
      }
      &:hover, &.active {
        box-shadow: 1px 1px 5px 0px rgba(0,0,0,0.5);
        background: rgba(@red ,0.3);
        &.red {
          background: rgba(@red ,0.3);
        }
        &.cyan {
          background: rgba(@cyan ,0.3);
        }
        &.purple {
          background: rgba(@dark-violet ,0.3);
        }
        &.blue {
          background: rgba(blue ,0.3);
        }
        &.yellow {
          background: rgba(yellow ,0.3);
        }
        &.black {
          background: rgba(@very-dark-violet ,0.3);
        }
      }
      .detail-content {
        box-shadow: inset 1px 1px 5px 0px rgba(0,0,0,0.5);
        height: 100%;
        width: 100%;
        .detail-title {
          font-size: 24px;
          font-weight: bold;
          text-align: center;
          margin-top: 25px;
          display: flex;
          flex-direction: column;
          justify-content: center;
        }
        .col {
          padding: 25px;
          .row {
            width: 100%;
            margin: 10px 0;
            .label {
              font-weight: bold;
              min-width: 60px;
            }
            .description {
              border-bottom: 1px dotted @very-dark-blue;
              flex-grow: 1;
            }
          }
        }
      }
      .tile-content {
        padding: 25px;
        height: 200px;
        width: 200px;
        cursor: pointer;
        .tile-image {
          display: flex;
          justify-content: center;
          height: inherit;
          width: inherit;
          img {
            height: inherit;
          }
        }
      }
    }
  }
}

</style>
