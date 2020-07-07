<template>
  <div class="content" :class="content.page">
      <h2 class="content-title">{{content.title}}</h2>
      <div class="content-container">
        <section
        v-for="section in content.sections"
        :key="section.type"
        @click="openSection(section.type)">
          <h2 class="section-title">{{section.title}}</h2>
          <div class="entry" v-for="entry in section.entries" :key="entry.id">
            <div class="col">
              <h3 v-if="entry.titleMain" class="section-main-title">{{entry.titleMain}}</h3>
              <div class="row align-bot">
                <h3 class="entry-title">{{entry.title}}</h3>
                <h4 class="entry-subtitle" v-if="entry.subtitle">{{entry.subtitle}}</h4>
              </div>
              <p class="text" v-for="paragraph in entry.text" :key="paragraph">
                <ion-icon v-if="section.type == 'school'" name="school-outline"/>
                <ion-icon v-if="section.type == 'work'" name="desktop-outline"/>
                <ion-icon v-if="section.type == 'volunteering'" name="football-outline"/>
                {{paragraph}}
                </p>
            </div>
            <span class="image" v-if="entry.image">
              <img :src="require(`@/assets/` + entry.image)">
            </span>
          </div>
        </section>
      </div>
  </div>
</template>

<script>
export default {
  name: 'ContentComponent',
  props: ['content', 'background', 'linkColor', 'hoverBackground'],
  data: () => ({
    sectionActive: '',
  }),
  methods: {
    openSection(sectionType) {
      if (sectionType === this.sectionActive) {
        this.sectionActive = '';
      } else {
        this.sectionActive = sectionType;
      }
    },
  },
};
</script>

<style lang="less">
@import './../assets/styles/global.less';
.about {
  .content {
    height: 100vh;
    padding-left: 350px;
    display: flex;
    flex-direction: column;
    justify-items: center;
      .content-title {
        position: relative;
        font-size: 48px;
        font-weight: lighter;
        margin-top: 20px;
        margin-bottom: 0;
        padding-bottom: 25px;
        &::after {
          content: ' ';
          position: absolute;
          left: -50px;
          bottom: 0;
          height: 10px;
          width: calc(100% + 50px);
          box-shadow: 0 5px 5px -5px @dark-violet;
        }
      }
    .content-container {
      overflow-y: scroll;
      height: calc(100vh - 100px);
      section {
        display: flex;
        flex-direction: column;
        color: @dark-violet;
        padding: 25px 0;
        border-bottom: 1px solid @gray;
        .section-title {
          font-size: 40px;
        }
        .entry {
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          width: 80%;
          padding-bottom: 25px;
          .entry-title {
            font-size: 30px;
            margin: 0;
          }
          .entry-subtitle {
            font-size: 24px;
            margin: 0;
            color: @grayish-violet;
          }
          .text {
            margin: 5px 0;
            display: flex;
            align-items: center;
            ion-icon {
              margin-right: 10px;
              min-width: 20px;
              max-width: 20px;
            }
          }
          .image {
            display: flex;
            align-items: center;
            img {
              max-height: 150px;
              max-width: 300px;
              transition: opacity 0.3s;
              transition-delay: 0.4s;
              -webkit-transition-delay: 1s;
              -webkit-transition: opacity 0.3s;
              opacity: 1;
            }
          }
        }
      }
    }
  }
}

</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  .align-bot {
    align-items: flex-end;
    margin-bottom: 15px;
    .entry-title {
      margin-right: 15px !important;
    }
  }

</style>
