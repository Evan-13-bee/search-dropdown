<template>
  <v-content>
    <v-container>
      <v-container>
        <v-row class="d-flex">
          <v-text-field
            v-model="search"
            label="Врач, заболевания, услуги"
            outlined
            clearable
            class="search"
            @focus="expand = true"
            @blur="expand = false"
          ></v-text-field
          >
          <v-btn
            color="primary"
            elevation="2"
            class="search__button"
            >Найти</v-btn
          >
        </v-row>
      </v-container>

      <v-expand-transition>
        <v-card
          tile
          v-if="filteredItems.length"
          class="overflow-auto items-list"
          v-show="expand"
        >
          <v-subheader class="items__subhead">Специальность</v-subheader>
          <v-list-item v-for="item in filteredItems" :key="item.id">
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-card>
        <v-card tile v-else class="overflow-auto items-list">
          <v-subheader class="items__subhead">Специальность</v-subheader>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Не найдено специальностей</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-card>
      </v-expand-transition>
    </v-container>
  </v-content>
</template>

<script>
export default {
  data: () => ({
    search: "",
    expand: false,
    items: [
      {
        title: "Аллерголог",
        id: "9440",
        url: "vrachi/allergolog",
        type: "spec",
      },
      {
        title: "Андролог",
        id: "11690",
        url: "vrachi/androlog",
        type: "spec",
      },
      {
        title: "Артролог",
        id: "7757",
        url: "vrachi/artrolog",
        type: "spec",
      },
      {
        title: "Вегетолог",
        id: "8385",
        url: "vrachi/vegetolog",
        type: "spec",
      },
      {
        title: "Вертебролог",
        id: "7758",
        url: "vrachi/vertebrolog",
        type: "spec",
      },
      {
        title: "Вертеброневролог",
        id: "7759",
        url: "vrachi/vertebronevrolog",
        type: "spec",
      },
      {
        title: "Висцеральный массажист",
        id: "8170",
        url: "vrachi/visczeralnyj-massazhist",
        type: "spec",
      },
      {
        title: "Висцеральный терапевт",
        id: "7760",
        url: "vrachi/visczeralnyij-terapevt",
        type: "spec",
      },
      {
        title: "Врач восточной медицины",
        id: "7763",
        url: "vrachi/vrach-vostochnoj-mediczinyi",
        type: "spec",
      },
      {
        title: "Врач китайской медицины",
        id: "7764",
        url: "vrachi/vrach-kitayskoy-mediciny",
        type: "spec",
      },
      {
        title: "Врач ЛФК",
        id: "7761",
        url: "vrachi/vrach-lfk",
        type: "spec",
      },
      {
        title: "Врач общей практики",
        id: "7765",
        url: "vrachi/vrach-obshhey-praktiki",
        type: "spec",
      },
      {
        title: "Врач первичного приёма",
        id: "7766",
        url: "vrachi/vrach-pervichnogo-priema",
        type: "spec",
      },
      {
        title: "Врач тибетской медицины",
        id: "7767",
        url: "vrachi/vrach-tibetskoy-mediciny",
        type: "spec",
      },
      {
        title: "Врач УВТ",
        id: "7762",
        url: "vrachi/vrach-uvt",
        type: "spec",
      },
      {
        title: "Врач УЗИ",
        id: "8386",
        url: "vrachi/vrach-uzi",
        type: "spec",
      },
      {
        title: "Гастроэнтеролог",
        id: "7768",
        url: "vrachi/gastroenterolog",
        type: "spec",
      },
      {
        title: "Гериатр",
        id: "8374",
        url: "vrachi/geriatr",
        type: "spec",
      },
      {
        title: "Геронтолог",
        id: "8375",
        url: "vrachi/gerontolog",
        type: "spec",
      },
      {
        title: "Гинеколог",
        id: "8387",
        url: "vrachi/ginekolog",
        type: "spec",
      },
      {
        title: "Гинеколог-эндокринолог",
        id: "8388",
        url: "vrachi/ginekolog-endokrinolog",
        type: "spec",
      },
      {
        title: "Гипнотерапевт",
        id: "7771",
        url: "vrachi/gipnoterapevt",
        type: "spec",
      },
      {
        title: "Гирудолог",
        id: "7772",
        url: "vrachi/girudolog",
        type: "spec",
      },
      {
        title: "Гирудотерапевт",
        id: "7773",
        url: "vrachi/girudoterapevt",
        type: "spec",
      },
      {
        title: "Гомеопат",
        id: "7774",
        url: "vrachi/gomeopat",
        type: "spec",
      },
    ],
  }),
  computed: {
    filteredItems() {
      let search = this.search ? this.search.toLowerCase() : "";
      return this.items.filter((e) => e.title.toLowerCase().includes(search));
    },
  },
  methods: {},
};
</script>
<style lang="scss">
.items-list {
  height: 280px;
  &::-webkit-scrollbar {
    width: 6px; /* width of the entire scrollbar */
  }
  &::-webkit-scrollbar-thumb {
    background-color: #387aff;
    border-radius: 20px;
  }
}
.items {
  &__subhead {
    border-bottom: 1px solid #9cbdff;
    font-style: normal;
    font-weight: 400;
    font-size: 13px;
    line-height: 16px;
    display: flex;
    align-items: center;
    letter-spacing: 0.2px;
    color: #808080;
  }
}
.search {
  margin-bottom: -15px;
  .v-input__control {
    .v-input__slot {
      margin-bottom: -15px;
    }
  }
  &__button {
    height: 55px !important;
    border-radius: 10px !important;
    width: 105px;
    margin-left: 10px;
  }
}
</style>
