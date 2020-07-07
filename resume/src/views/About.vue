<template>
  <div class="about">
    <content-component :content="content"/>
  </div>
</template>

<script>
// @ is an alias to /src
import ContentComponent from '@/components/ContentComponent.vue';

export default {
  name: 'About',
  components: {
    ContentComponent,
  },
  data: () => ({
    color: 'home',
    content: {
      title: 'Šimiho lajf',
      sections: [
        {
          type: 'school',
          title: 'Škola',
          entries: [
            {
              id: 1,
              title: 'FEI STU',
              subtitle: '(od 2015)',
              position: 'Študent Ing.',
              text: [
                'Odbor aplikovaná informatika - Modelovanie Udalostných Systémov',
                'Bakalársky projekt - Multiplayer hra pre Android',
              ],
              image: 'logo/stu.png',
            },
            {
              id: 2,
              title: 'TTU Tallinn',
              subtitle: '(2017-2018) Erasmus+ Estónsko',
              position: 'Výmenný študent',
              text: [
                'Fungovanie eGovernmentu v Estónsku a vo zvyšku sveta',
                'Základy programovania web stránok v Asp.Net',
                'Teoretický výskum a vývoj prototypu snímacieho zariadenia pre preklad znakovej reči do angličtiny',
                'Asynchrónne programovanie (C, C++)',
              ],
              image: 'logo/ttu.jpg',
            },
          ],
        },
        {
          type: 'work',
          title: 'Práca',
          entries: [
            {
              id: 1,
              title: 'Angular Developer',
              subtitle: '(február 2019 - jún 2020)',
              text: [
                'Vývoj webových systémov vo frameworku Angular2+',
                'Komunikácia so zákazníkom',
                'Angular workshop leader na Strednej priemyselnej škole technickej Karola Adlera',
              ],
              image: 'logo/angular.png',
            },
            {
              id: 2,
              title: 'Junior Developer',
              subtitle: '(máj 2018 - október 2018)',
              text: [
                'Redizajn starých web do responzívnej podoby (HTML, CSS, Javascript)',
                'Bugfix mobilných aplikácií (Android)',
              ],
              image: 'logo/android.png',
            },
          ],
        },
        {
          type: 'volunteering',
          title: 'Dobrovolníctvo',
          entries: [
            {
              id: 1,
              title: 'IAESTE',
              type: 'volunteering',
              subtitle: '(2016-2019)',
              text: [
                '3x Hlavný organizátor série soft-skillových školení Training Day.',
                'Letný koordinátor zahraničných stážistov.',
                'Účastník medzinárodných konferencií v Maďasku a Tunise.',
              ],
              image: 'logo/iaeste.png',
            },
          ],
        },
      ],
    },
  }),

};
</script>
