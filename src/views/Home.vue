<template>
  <v-app id="inspire" :style="{background: $vuetify.theme.themes.dark.background}">
    <SideBar/>
    <SideBarRight/>
    <v-container>
      <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n4">
        <v-btn-toggle v-model="toggle_exclusive" tile group color="#4bb9e5">
          <v-btn text>
            <v-icon>fas fa-arrow-left</v-icon>
          </v-btn>
          <v-btn text>
            <v-icon>fas fa-arrow-right</v-icon>
          </v-btn>
        </v-btn-toggle>
        <v-spacer></v-spacer>
        <v-col lg="4" cols="12">
          <v-form class="mt-6 mr-n4">
            <v-text-field rounded outlined dense placeholder="Search..." append-icon="fas fa-search"/>
          </v-form>
        </v-col>
      </v-toolbar>

      <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n5">
        <v-toolbar-title class="_title">Sprint overview</v-toolbar-title>
        <v-btn color="#4bb9e5" text class="ml-5">
          last sprint
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn color="#4bb9e5" class="rounded-lg _btn" small dark >
          Finish sprint
        </v-btn>
      </v-toolbar>

      <v-item-group mandatory class="mt-n4">

        <v-container>
          <v-row justify="center" class="space">

            <v-col cols="12" md="2" sm="12">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-list-item three-line class="mt-7">
                        <v-list-item-content>
                          <div class="mb-4">
                            <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-chart-bar</v-icon>
                          </div>
                          <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">Team velocity</v-list-item-subtitle>
                          <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>52</strong></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="2">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-list-item three-line class="mt-7">
                        <v-list-item-content>
                          <div class="mb-4">
                            <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-user</v-icon>
                          </div>
                          <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">Team member</v-list-item-subtitle>
                          <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>12</strong></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="2">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-list-item three-line class="mt-7">
                        <v-list-item-content>
                          <div class="mb-4">
                            <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-suitcase</v-icon>
                          </div>
                          <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">Tasks delivered</v-list-item-subtitle>
                          <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>23</strong></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="2">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-list-item three-line class="mt-7">
                        <v-list-item-content>
                          <div class="mb-4">
                            <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-user</v-icon>
                          </div>
                          <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">Team member</v-list-item-subtitle>
                          <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>12</strong></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="2">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                    <v-list-item three-line class="mt-7">
                      <v-list-item-content>
                      <div class="mb-4">
                        <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-search</v-icon>
                      </div>
                      <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">Spikes delivered</v-list-item-subtitle>
                      <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>23</strong></v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

            <v-col cols="12" md="2">
              <v-item v-slot="{active, toggle}">
                <v-card :color="active ? '#4bb9e5' : 'white'"
                class="d-flex align-center rounded-lg"
                dark
                height="150"
                @click="toggle"
                >
                  <v-row>
                    <v-col cols="12" sm="12">
                      <v-list-item three-line class="mt-7">
                        <v-list-item-content>
                          <div class="mb-4">
                            <v-icon x-large :color="active ? 'white' : '#4bb9e5'">fas fa-globe-africa</v-icon>
                          </div>
                          <v-list-item-subtitle :class="active ? 'white--text' : 'black--text'">News events</v-list-item-subtitle>
                          <v-list-item-title class="headline mb-1" :class="active ? 'white--text' : 'black--text'"><strong>15</strong></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-col>
                  </v-row>
                </v-card>
              </v-item>
            </v-col>

          </v-row>
        </v-container>
        
      </v-item-group>

      <v-row class="mt-n4">
        <v-col cols="12" md="6">
          <!-- <v-chart class="chart mt-2" :option="option"/> -->
          <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n3">
            <v-toolbar-title class="_title">Tasks stories</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn rounded small class="rounded-lg _btn" color="#4bb9e5">See all</v-btn>
          </v-toolbar>
          <v-simple-table class="mt-n1">
            <template v-slot:default>
              <tbody>
                <tr v-for="item in orders" :key="item.name">
                  <td>{{item.id}}</td>
                  <td>{{item.title}}</td>
                  <td>{{item.state}}</td>
                  <td>{{item.count}}</td>
                  <td>
                    <v-btn icon>
                      <v-icon small>{{item.icon}}</v-icon>
                    </v-btn>
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-col>

        <v-col cols="12" md="6" sm="12">
          <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n3">
            <v-toolbar-title class="_title">Sprint stories</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn rounded small class="rounded-lg _btn" color="#4bb9e5">See all</v-btn>
          </v-toolbar>
          <v-simple-table class="mt-n1">
            <template v-slot:default>
              <tbody>
                <tr v-for="item in orders" :key="item.name">
                  <td>{{item.id}}</td>
                  <td>{{item.title}}</td>
                  <td>{{item.state}}</td>
                  <td>{{item.count}}</td>
                  <td>
                    <v-btn icon>
                      <v-icon small>{{item.icon}}</v-icon>
                    </v-btn>
                  </td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
        </v-col>
      </v-row>

      <v-toolbar color="rgba(0,0,0,0)" flat class="mt-n4">
        <v-toolbar-title class="_title">Team members</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn rounded small class="rounded-lg _btn" color="#4bb9e5">Add member</v-btn>
      </v-toolbar>

      <v-card class="rounded-lg mt-2">
        <v-row>
          <v-col cols="12" sm="3">
            <v-list subheader two-line>
              <v-list-item>
                <v-badge bordered bottom color="#49D9A0" dot offset-x="28" offset-y="22">
                  <v-list-item-avatar>
                    <v-avatar size="40">
                      <v-img src="https://randomuser.me/api/portraits/women/2.jpg"></v-img>
                    </v-avatar>
                  </v-list-item-avatar>
                </v-badge>
                <v-list-item-content>
                  <v-list-item-title class="title_">AAE IdeaPro</v-list-item-title>
                  <v-list-item-subtitle>32 Story point</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>

          <v-col cols="12" sm="3">
            <v-list subheader two-line>
              <v-list-item>
                <v-badge bordered bottom color="#49D9A0" dot offset-x="28" offset-y="22">
                  <v-list-item-avatar>
                    <v-avatar size="40">
                      <v-img src="https://randomuser.me/api/portraits/women/2.jpg"></v-img>
                    </v-avatar>
                  </v-list-item-avatar>
                </v-badge>
                <v-list-item-content>
                  <v-list-item-title class="title_">John Doe</v-list-item-title>
                  <v-list-item-subtitle>48 Story point</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>

          <v-col cols="12" sm="3">
            <v-list subheader two-line>
              <v-list-item>
                <v-badge bordered bottom color="#49D9A0" dot offset-x="28" offset-y="22">
                  <v-list-item-avatar>
                    <v-avatar size="40">
                      <v-img src="https://randomuser.me/api/portraits/women/2.jpg"></v-img>
                    </v-avatar>
                  </v-list-item-avatar>
                </v-badge>
                <v-list-item-content>
                  <v-list-item-title class="title_">Kang So Ra</v-list-item-title>
                  <v-list-item-subtitle>130 Story point</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>

          <v-col cols="12" sm="3">
            <v-list subheader two-line>
              <v-list-item>
                <v-badge bordered bottom color="#49D9A0" dot offset-x="28" offset-y="22">
                  <v-list-item-avatar>
                    <v-avatar size="40">
                      <v-img src="https://randomuser.me/api/portraits/women/2.jpg"></v-img>
                    </v-avatar>
                  </v-list-item-avatar>
                </v-badge>
                <v-list-item-content>
                  <v-list-item-title class="title_">Jin Se Young</v-list-item-title>
                  <v-list-item-subtitle>95 Story point</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-col>
        </v-row>
      </v-card>

    </v-container>
  </v-app>
</template>

<script>
import SideBar from '../components/SideBar.vue'
import SideBarRight from '../components/SideBarRight.vue'
import {use} from 'echarts/core'
import {CanvasRenderer} from 'echarts/renderers'
import {PieChart} from 'echarts/charts'
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent,
}from 'echarts/components';
// import VChart, {THEME_KEY} from 'vue-charts';


use([
  CanvasRenderer,
  PieChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent
])

  export default {
    name: 'Home',
    
    data: () =>({
      toggle_exclusive: 1,
      orders:[
        {
          id: 'P42',
          title: 'Onboarding',
          state: 'Delivred',
          count: 3,
          icon: 'fas fa-ellipsis-h'
        },
        {
          id: 'P32',
          title: 'User profile',
          state: 'Delivred',
          count: 8,
          icon: 'fas fa-ellipsis-h'
        },
        {
          id: 'P56',
          title: 'Langing page',
          state: 'Approved',
          count: 12,
          icon: 'fas fa-ellipsis-h'
        },
        {
          id: 'P36',
          title: 'Settings',
          state: 'Approved',
          count: 9,
          icon: 'fas fa-ellipsis-h'
        }
      ],
      option: {
        title: {
          text: "Burnsown chart",
          left: "left"
        },
        tooltip: {
          trigger: "item",
          formatter: "{a} <br/>{b} : {c} ({d}%)"
        },

        series: [
          {
            name: "Traffic Source",
            type: "pie",
            radius: "55%",
            center: ["45%", "50%"],
            data: [
              {value: 335, name: "Direct"},
              {value: 310, name: "Email"},
              {value: 234, name: "Ad Networks"},
              {value: 135, name: "Video Ads"},
              {value: 1548, name: "Search Engines"}
            ],
            emphasis: {
              itemStyle: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: "rgba(0,0,0,0)"
              }
            }
          }
        ]

      }
    }),
    components: {
        SideBar,
        SideBarRight,
        // VChart
    },
    // provide: {
    //   [THEME_KEY]: "green"
    // }
  }
</script>
<style>

  @media only screen and(max-width: 789px) {
    .space{
      margin-left: -100px;
      margin-right: -100px;
    }
  }
  .space{
    margin-left: 0;
    margin-right: 0;
  }
  
</style>