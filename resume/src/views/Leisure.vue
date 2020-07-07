<template>
  <div class="leisure">
    <img class="background" src="@/assets/images/leisure.jpg">
    <div class="content-grid">
        <div class="box header">
            <h2 class="title">Koníčky a iné zvery</h2>
        </div>
        <div class="box content">
            <div class="card"  v-for="activity in activities" :key="activity.id">
                <div class="row">
                    <div class="col">
                        <h3 class="card-title">{{activity.title}}</h3>
                        <p class="card-text" v-for="text in activity.text" :key="text">{{text}}</p>
                    </div>
                    <span class="col card-image">
                        <img :src="require(`@/assets/` + activity.image)">
                    </span>
                </div>
            </div>
        </div>
        <div class="box footer">
            <div class="footer-content">
                <p>Ďakujem že ste si našli čas a prečtali môj TED talk.</p>
                <p>V prípade záujmu ma kontaktujte na maile uvedenom v kontaktoch. CVčko dostupné tu
                    <button>RESUME</button>
                </p>
            </div>
        </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Leisure',
  data: () => ({
    activities: [
      {
        id: 1,
        title: 'Šport',
        text: [
          'Hodiny sedenia v kancelárií najradšej vyvažujem pravidelným behom, bicyklovaním alebo horskou turistikou.',
          'V zime outdoorove aktivity nahrádzam posilkou',
        ],
        image: 'logo/vue.png',
      },
      {
        id: 2,
        title: 'Socializácia',
        text: [
          'Počas piatkových nocí a sobotných rán ma môžete stretnúť reprezentovať Slovenskú kultúru v uliciach hlavného mesta. Medzi moje aktívne barové záľuby patrí shisha, hranie doskových hier a súťaženie na Pub Kvízoch.',
        ],
        image: 'logo/vue.png',
      },
      {
        id: 3,
        title: 'Cestovanie',
        text: [
          'V minulosti som ubytovával a sprevádzal turistov v Bratislave cez portál Couchsurfing',
          'Obľubujem cestovanie na ľahko, bez plánu a hľadanie ubytovania na poslednú chvíľu.',
          'Obľúbené mesto: Barcelona',
        ],
        image: 'logo/vue.png',
      },
      {
        id: 4,
        title: 'Netflix & Chill',
        text: [
          'Mojou hlavnou antisociálnou aktivitou je hranie hier a čítanie kníh a popíjanie kávy počas obednej prestávky',
          'Knižný autory: Terry Pratchett, George Orwell',
          'Herné série: Hollow Knight, Diablo 2',
          'Filmy/Seriály: Green Book, Final Space',
        ],
        image: 'logo/vue.png',
      },
    ],
  }),

};
</script>

<style lang="less">
@import './../assets/styles/global.less';

.leisure {
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
    gap: 50px 10px;
    grid-template-areas:
    "header"
    "content"
    "footer"
  }
  .content {
    grid-area: content;
    padding: 0 20px;
    height: calc(100vh - 300px);
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 1fr;
    gap: 20px 20px;
    grid-template-areas: ". ." ". .";
    .card {
        position: relative;
        justify-content: space-between;
        box-shadow: 0px 1px 5px 0px rgba(0,0,0,0.5);
        width: 100%;
        display: flex;
        background: rgba(white ,0.4);
        .row {
            height: 100%;
            justify-content: space-between;
        }
        .card-image {
            position: relative;
            img {
                height: 100px;
                width: auto;
                padding: 25px;
            }
        }
        .card-title {
            margin-top: 30px;
            padding: 0 25px;
        }
        .card-text {
            padding: 0 25px;
            margin: 5px 0;
        }
        &:nth-of-type(1) {
            flex-direction: column;
            .card-image {
                align-self: flex-end;
            }
            &:hover {
                background: rgba(@cyan ,0.2);
            }
        }
        &:nth-of-type(2) {
            .row {
                flex-direction: row-reverse;
            }
            .card-image {
                align-self: flex-end;
            }
            &:hover {
                background: rgba(@gray ,0.2);
            }
        }
        &:nth-of-type(3) {
            flex-direction: column;
            .card-image {
                align-self: flex-start;
            }
            &:hover {
                background: rgba(@dark-violet ,0.2);
            }
        }
        &:nth-of-type(4) {
            flex-direction: column-reverse;
            .row {
                flex-direction: row-reverse;
            }
            .card-image {
                align-self: flex-start;
            }
            &:hover {
                background: rgba(@red ,0.2);
            }
        }
    }
  }
  .header {
    grid-area: header;
    display: flex;
    flex-direction: row;
    background: rgba(white ,0.6);
    box-shadow: 0px 1px 5px 0px rgba(0,0,0,0.5);
    z-index: 2;
    height: 100px;
    .title {
        width: 100%;
        margin: 0;
        text-align: center;
        align-self: center;
    }
  }
  .footer {
    grid-area: footer;
    display: flex;
    width: 100%;
    z-index: 2;
    background: rgba(white ,0.6);
    box-shadow: 0px 1px 5px 0px rgba(0,0,0,0.5);
    height: 100px;
    .footer-content {
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 0 25px;
        p {
            margin: 5px 0;
        }
    }
  }
}

</style>
