<template>
  <div>
    <b-container fluid>
      <div class="d-flex flex-row justify-content-center flex-wrap">
        <b-row cols="1" cols-sm="1" cols-md="1" cols-lg="2" class="mt-5">
          <b-col
            v-for="(noticia, index) of listaNoticias"
            :key="index"
          >
            <b-container>
              <b-card
                :title="`${noticia.title}`"
                :img-src="`${noticia.urlToImage}`"
                img-alt="Image"
                img-top
              >
                <b-card-text>
                  {{ noticia.description }}
                </b-card-text>
                <b-button
                  :href="`${noticia.url}`"
                  target="_blank"
                  variant="primary"
                  >Ver más</b-button
                >
                <template #footer>
                  <em>Publicado: {{ noticia.publishedAt }}</em>
                </template>
              </b-card>
            </b-container>
          </b-col>
        </b-row>
      </div>
    </b-container>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "News",
  props: ["new"],

  data: () => ({
    noticia: {
      author: "",
      description: "",
      title: "",
      urlToImage: "",
      publishedAt: "",
      url: "",
    },
    listaNoticias: [],
  }),
  methods: {
    async getNews() {
      let news = await axios.get(
        `https://newsapi.org/v2/top-headlines?country=us&apiKey=eae8e746b0344026a77c81c09404066b`
      );
      return news;
    },
  },
  async created() {
    let noticias = await this.getNews();
    let num = Math.floor((Math.random()*10)+1);    
    let noticias1 = noticias.data.articles;
    noticias1 = noticias1.slice(num, num+4);   
    return (this.listaNoticias = noticias1);
  },
};
</script>