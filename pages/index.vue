<template>
  <div>
      <div class="mainBg">
        <v-container class="pt-10">
          <v-row>
            <v-col class="d-flex align-center" cols="12" md="6" >
              <div class="d-flex align-center" style="flex-flow:column">
                <div style="text-align:center;color:#131545;font-size:5em;line-height: 1;font-weight: 900;"  >ASO TEGAL</div>
                <div  class="d-flex" style="font-size:1.2em;line-height: 1">
                  <div></div>
                  <div style="background-color:#000;border:3px solid #000; " class="white--text pa-2">GATHERING</div>
                  <div style="background-color:#fff;border:3px solid #000; font-size:0.8em" class="d-flex align-center justify-center black--text pa-2"> 5-6 November 2022</div>
                </div>
                <div class="mt-3"><v-chip class="primary" style="font-weight:bold"><v-icon small class="white--text">mdi-map-marker</v-icon>GRAND DIAN - GUCI</v-chip></div>
              </div>
            </v-col>
            <v-col cols="12" md="6">
              <img src="img/title.png" width="100%" />
            </v-col>
          </v-row>
        </v-container>
      </div>
      <div>
        <v-container>
          <div class="pt-10 d-flex align-center justify-center mb-10" style="flex-flow:column">
            <div class="d-flex justify-center"><h2>OVERVIEW VENUE</h2></div>
            <div class="pinkLine"></div>
          </div>
          <v-row >
            <v-col cols="6" md="4" v-for="item,index in 6" :key="index">
              <img :src="'/img/ven'+(index+1)+'.jpg'" width="100%" style="border-radius:15px">
            </v-col>
          </v-row>
        </v-container>
      </div>
      <div>
        <v-container>
          <v-row>
            <v-col cols="12">
                <div class="pt-10 d-flex align-center justify-center mb-10" style="flex-flow:column">
                  <div class="d-flex justify-center" ><h2>Preparation</h2></div>
                  <div class="pinkLine"></div>
                </div>
                <v-container>
                  <v-row>
                    <v-col cols="12" class="d-flex justify-center">
                      <div style="width:100%;max-width:500px;border-radius:15px;" class="elevation-5 pa-5 ">
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Outfit 90an (colorful)</div>
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Baju renang</div>
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Baju olah raga</div>
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Jaket</div>
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Obat2 pribadi</div>
                        <div><v-icon class="green--text mr-3">mdi-check-circle</v-icon>Alat ibadah</div>
                      </div>
                    </v-col>
                  </v-row>
                </v-container>

            </v-col>
          </v-row>
        </v-container>
      </div>
      <div class="d-flex justify-center" >
        <div style="flex-grow:1;max-width:1000px" class="bg2">
          <v-container>
              <div class="pt-10 d-flex align-center justify-center mb-10" style="flex-flow:column">
                  <div class="d-flex justify-center" ><h2>Rundown</h2></div>
                  <div class="pinkLine"></div>
                </div>

                <v-row>
                  <v-col cols="12" class="text-center">
                    <v-chip class="pink white--text">Sabtu, 5 November 2022</v-chip>
                  </v-col>
                  <v-col cols="12">

                    <v-timeline
                        align-top
                        :dense="$vuetify.breakpoint.smAndDown"
                      >
                        <v-timeline-item
                          v-for="(item, i) in items"
                          :key="i"
                          :color="item.color"
                          :icon="item.icon"
                          fill-dot
                        >
                          <v-card
                            :color="item.color"
                        
                            dark
                          >
                            <v-card-title class="text-h6">
                              <div v-if="$vuetify.breakpoint.smAndDown" style="font-size:0.8em">
                                {{item.title}}
                              </div>
                              <div v-else>
                                {{item.title}}
                              </div>
                            </v-card-title>
                            <v-card-text class="white text--primary pt-5" v-if="item.text">
                              <div>
                                <img v-if="item.img" :src="item.img" width="250px"/>
                              </div>
                              <v-chip v-if="item.tag" class="purple mb-3 mt-3"><b>{{item.tag}}</b></v-chip>
                              <div v-html="item.text"></div>
                              <v-btn
                                  v-if="item.detail"
                                  :color="item.color"
                                  class="mx-0 mt-3"
                                  @click="entDetail = true"
                                  outlined
                                >
                                  Detail
                                </v-btn>
                            </v-card-text>
                          </v-card>
                        </v-timeline-item>
                      </v-timeline>
                  </v-col>
                </v-row>
            </v-container>
        </div>
      </div>
      <div class="d-flex justify-center" >
        <div style="flex-grow:1;max-width:1000px" class="bg2">
          <v-container>

                <v-row>
                  <v-col cols="12" class="text-center">
                    <v-chip class="pink white--text">Minggu, 6 November 2022</v-chip>
                  </v-col>
                  <v-col cols="12">

                    <v-timeline
                        align-top
                        :dense="$vuetify.breakpoint.smAndDown"
                      >
                        <v-timeline-item
                          v-for="(item, i) in items2"
                          :key="i"
                          :color="item.color"
                          :icon="item.icon"
                          fill-dot
                        >
                          <v-card
                            :color="item.color"
                        
                            dark
                          >
                            <v-card-title class="text-h6">
                              {{item.title}}
                            </v-card-title>
                            <v-card-text class="white text--primary pt-5" v-if="item.text">
                              <div>
                                <img v-if="item.img" :src="item.img" width="250px"/>
                              </div>
                              <div v-html="item.text"></div>
                            </v-card-text>
                          </v-card>
                        </v-timeline-item>
                      </v-timeline>
                  </v-col>
                </v-row>
            </v-container>
        </div>
      </div>

      <v-dialog v-model="entDetail" width="500px">
        <v-card class="pa-5">
          <b>Entertainment</b>
          <img src="/img/run8.jpg" style="width:100%;border-radius:20px"/>
          <div>1. Biduan Dangdut dan Pop</div>
          <div>2. Foya Koya</div>
          <v-divider class="my-5"></v-divider>
          <b>Doorprize</b>
          <div class="mt-3"><i>Berlangsung setelah gala dinner</i></div>
          <div class="mt-3"><b>Sesi 1:</b> 20.00 - 20.15</div>
          <div><b>Sesi 2:</b> 20.30 - 20.45</div>
          <div><b>Sesi 3:</b> 21.15 - 21.30</div>
        </v-card>
      </v-dialog>

  </div>

</template>

<style scoped>
  .mainBg {
    background:url('/img/bg.jpg');
  }

  .pinkLine {
    width:150px;
    height:12px;
    background: linear-gradient(90deg, #F474E0 15.32%, #968DFF 87.93%);
    border-radius: 6px;
  }

  .bg2 {
  }
</style>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data(){
    return {
      entDetail:false,
      items: [
        {
          color: 'red lighten-2',
          icon: 'mdi-car-outline',
          title:'(08.00) Berangkat',
          img:'/img/run1.jpg',
          text:'<table><tr><td>Seragam</td><td class="pr-2" ">:</td><td style="font-weight:bold"> Jersey outbound</td> </tr><tr><td >Tegal</td><td>:</td style="font-weight:bold"> <td style="font-weight:bold">Tegal</tr><tr></td><br/><td>DPC</td><td>:</td> <td style="font-weight:bold">Pekalongan</td></tr></table>'
        },
        {
          color: 'purple darken-1',
          icon: 'mdi-account-multiple-check',
          title:'(10.00) Kumpul di Hotel Grand Dian - Guci'
        },
        {
          color: 'green lighten-1',
          icon: 'mdi-airballoon',
          img:'/img/run3.jpg',
          title:'(10.00 - 12.00) Outbound',
          text:'Tempat: <b>Hotel Grand Dian - Guci</b>'
        },
        {
          color: 'blue lighten-1',
          icon: 'mdi-food',
          img:'/img/run4.jpg',
          title:'(12.00 - 14.00) Lunch (ISHOMA)',
          text:'Tempat: <b>Hall Antasena</b>'
        },
        {
          color: 'brown lighten-1',
          icon: 'mdi-coffee',
          img:'/img/run5.jpg',
          title:'(14.00 - 17.00) Coffee Break',
          text:'Tempat: <b>Pool Grand Dian</b>'
        },
        {
          color: 'pink lighten-1',
          icon: 'mdi-account-network',
          title:'(17.00 - 19.00) Prepare Gala Dinner',
        },
        {
          color: 'black lighten-1',
          icon: 'mdi-spoon-sugar',
          img:'/img/run7.jpg',
          title:'(19.00 - 20.00) Gala Dinner',
          text:'Dress code: Outfit ala 90 an (colorful)'
        },
        {
          color: 'blue lighten-1',
          icon: 'mdi-guy-fawkes-mask',
          title:'(20.00 - 23.00) Entertainment & Doorprize',
          detail:'entertainment',
          tag:'Outfit ala 90 an (colorful)',
          img:'/img/hib1.jpg',
          text:'<b>Entertainment</b><br/>1. Biduan Dangdut dan Pop<br/>2. Foya Koya<br/><b>Doorprize</b><br/>iQos, Huawei Band, Anker Soundcor, Voucher MAP<br/><b>Pengumuman pemenang outbound</b>'
        },
        {
          color: 'grey darken-1',
          icon: 'mdi-bunk-bed',
          title:'(23.00) Istirahat',
        },
      ],
      
      items2: [
        {
          color: 'red lighten-2',
          icon: 'mdi-run',
          title:'(07.00 - 08.00) Senam Pagi',
          text:'Tempat: <b>Open Space Front Hall Antasena</b><br/><div class="mt-5"><b>Doorprize</b><br/>Huawei Band, Anker Soundcor, Voucher MAP</div>'
        },  
        {
          color: 'blue lighten-2',
          icon: 'mdi-food',
          title:'(08.00 - 09.00) Breakfast',
          text:'Tempat: <b>Hall Antasena</b>'
        },   
        {
          color: 'green lighten-2',
          icon: 'mdi-check-network',
          title:'(09.00 - 10.00) Prepare Pulang',
        },    
        {
          color: 'black',
          icon: 'mdi-alert-circle-check',
          title:'(10.00) Check out',
        }
      ]
    }
    
  }
}
</script>
