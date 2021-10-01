<template>
  <v-flex> 
    <div style="position: absolute; left:120px; top:40px;">
    <div v-for="(item, index) in isimler" :key="item.id">
      <v-btn
      rounded
      color="#303A2B"
      dark
      block
      class="mt-2"
      @click="Kisi(index)"
      >
      {{item.isim}}
      </v-btn>   
    </div>
    </div>
  
  <v-row justify="center" style="min-height: 160px; margin-top:200px;">
    <div class="mx-4 hidden-sm-and-down"></div>

    <v-col class="shrink">
      <v-btn class="ma-2" color="primary" @click="SoruSec()" x-large>
        Rastgele Soru
      </v-btn>

      <v-expand-x-transition >
        <v-card
          v-show="expand2"
          height="250"
          width="205"
          class="mx-auto mt-8"
          :color="KartRengi"
          >
          <v-flex class="pa-2">
            <div style="text-align:center; position:relative; top:65px;">
          <a style="color:black;"> 
          {{SorulanSoru}}
          </a>
            </div>
          </v-flex>
        </v-card>
      </v-expand-x-transition>
    </v-col>
  </v-row>
  </v-flex>
</template>

<script>
  export default {
    data: () => ({
      expand2: false,
      isimler:[
        {isim: "Örnek İsim 1"},
        {isim: "Örnek İsim 2"},
        {isim: "Örnek İsim 3"},
        {isim: "Örnek İsim 4"},
        {isim: "Örnek İsim 5"},
        {isim: "Örnek İsim 6"},
        {isim: "Örnek İsim 7"},
        {isim: "Örnek İsim 8"},
        {isim: "Örnek İsim 9"},
        {isim: "Örnek İsim 10"},
        {isim: "Örnek İsim 11"},
        {isim: "Örnek İsim 12"},
      ],
      Sorular: [
        {
          soru: "İlkokuldayken arkadaşının silgisini çaldın mı?",
          color: "#fce803",
        },
        {
          soru: "Yere düşen yemeği yedin mi?",
          color: "#fc7703",
        },
        {
          soru: "Hiç dolu dolu alışveriş yapıp kasa da paran olmadığını farkedip bütün ürünleri bırakmak zorunda kaldın mı?",
          color: "#fc4903",
        },
        {
          soru: "Yolda yürürken tanıdığını görünce telefonla konuşur gibi yapıp muhabbetten kaçtın mı?",
          color: "#ff0808",
        },
        {
          soru: "Yürüyen merdivende yukarı yönünde çıkıp aşağı yönünde koştun mu?",
          color: "#A18235",
        },
        {
          soru: "Yolda bağıra bağıra şarkı söyledin mi?",
          color: "#c5ff08",
        },
        {
          soru: "Toplu bir ortam da kimsenin gülmediği bir şeye sen kahkahalarla güldün mü",
          color: "#87ff08",
        },
        {
          soru: "Hiç okumadığın bir kitabı okumuş gibi yapıp, sonrasında okumadığının anlaşıldığı oldu mu",
          color: "#4bd411",
        },
        {
          soru: "Hiç evinin camından aşağı bir şey attın mı?, attıysan hiç birine denk geldi mi?",
          color: "#08fcb3",
        },
        {
          soru: "Hiç birinin yaptığı yemeği beğenmeyip ona çaktırmadan ağzından yemeği çıkardığın oldu mu?",
          color: "#39fae7",
        },
        {
          soru: "Hiç doğum günün de veya başka bir zaman da gelen hediyeyi beğenmediğin ama beğenmiş gibi yaptığın oldu mu?",
          color: "#0de3ff",
        },
        {
          soru: "Hiç bir çay içip saatlerce bir kafede oturdun mu?",
          color: "#0dc2ff",
        },
        {
          soru: "Hiç kopya çekerken yakalandın mı?",
          color: "#38afff",
        },
        {
          soru: "Hiç ailene uyuma numarası yaptın mı?",
          color: "#5ca3ff",
        },
        {
          soru: "Hiç başka bir arabanın dikiz aynalarından kendine bakarken içerde birinin olduğunu farketmediğin oldu mu?",
          color: "#207ffa",
        },
        {
          soru: "Hiç sana hediye edilen bir şeyi başkasına hediye ettin mi?",
          color: "#5488f7",
        },
        {
          soru: "Hiç telefonu klozete düşürdün mü?",
          color: "#697dff",
        },
        {
          soru: "Hiç başkasının yaptığı bir işi kendin yapmış gibi gösterdin mi?",
          color: "#abb6ff",
        },
        {
          soru: "Hiç haksız olduğunu farkettiğin halde sırf inadından kavgaya haklıymışsın gibi devam ettiğin oldu mu?",
          color: "#afabff",
        },
        {
          soru: "Hiç ailenin imzasını taklit ederek imzaladığı bir belge oldu mu?",
          color: "#8a82ff",
        },
        {
          soru: "Hiç, Bir arkadaşının anısını kendi anınmış gibi anlattın mı?",
          color: "#9e7aff",
        },
      ],
    SorulanSoru: "",
    KartRengi: "#FNGH34",
    }),
    methods: {
      SoruSec (){
        this.expand2 = !this.expand2;
        if(this.expand2 == false){
        this.SorulanSoru = "";
        return ;
        }
        if(this.Sorular.length == 0 ){
          this.SorulanSoru = "SORU BİTTİ :)";
        }
        var randomNumber = Math.floor(Math.random()*this.Sorular.length);
        this.SorulanSoru = this.Sorular[randomNumber].soru;
        this.KartRengi = this.Sorular[randomNumber].color;
        this.Sorular.splice(randomNumber, 1);
        
      },
      Kisi(index){
        this.isimler.splice(index, 1);
      }
    }
  }
  
</script>
