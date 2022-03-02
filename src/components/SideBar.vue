<template>
    <v-navigation-drawer v-model="drawer" app color="white" mini-variant mini-variant-width="80">
        <v-avatar class="d-block text-center mx-auto mt-4" size="40">
            <v-icon color="#4bb9e5" large>fab fa-atlassian</v-icon>
        </v-avatar>

        <v-divider class="mx-1 my-5"></v-divider>

        <v-list flat class="mt-5">
            <v-list-item-group v-model="selectedItem">
                <v-list-item v-for="(item, index) in items" :key="index" active-class="border" :ripple="false">
                    <v-list-item-icon>
                        <v-icon v-text="item.icon"></v-icon>
                    </v-list-item-icon>
                </v-list-item>
            </v-list-item-group>
        </v-list>
        
        <div style="position: absolute; bottom: 20px; margin-left: auto; margin-right: auto; left: 0; right: 0; text-align: center;">
            <v-divider class="mx-1 my-5"></v-divider>
            <v-menu >
                <template v-slot:activator="{on, attrs}">
                    <span v-bind="attrs" v-on="on" style="cursor: pointer" >
                        <v-badge offset-y="10" offset-x="10" color="red" class="mb-4" :content="notifs.length">
                            <v-icon>far fa-bell</v-icon>
                        </v-badge>
                    </span>
                </template>

                <v-list three-line width="300">
                    <template v-for="(item, index) in notifs">
                        <v-subheader 
                        v-if="item.header" 
                        :key="item.header" 
                        v-text="item.header"
                        ></v-subheader>

                        <v-divider
                        v-else-if="item.divider"
                        :key="index"
                        :inset="item.inset"
                        ></v-divider>

                        <v-list-item
                        v-else
                        :key="item.title"
                        link
                        >
                        <v-list-item-avatar>
                            <v-img :src="item.avatar"></v-img>
                        </v-list-item-avatar>

                        <v-list-item-content>
                            <v-list-item-title v-html="item.title"></v-list-item-title>
                            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
                        </v-list-item-content>
                        </v-list-item>
                    </template>
                </v-list>
                <v-btn small block>See all</v-btn>
            </v-menu>
            <br>
            <v-menu offset-y>
                <template v-slot:activator="{on, attrs}">
                    <span v-bind="attrs" v-on="on" style="cursor: pointer">
                        <v-badge offset-y="10" offset-x="10" color="red" class="mb-4" :content="messages.length">
                            <v-icon>fab fa-facebook-messenger</v-icon>
                        </v-badge>
                    </span>
                </template>

                <v-list three-line width="300">
                    <template v-for="(item, index) in messages">
                        <v-subheader 
                        v-if="item.header" 
                        :key="item.header" 
                        v-text="item.header"
                        ></v-subheader>

                        <v-divider
                        v-else-if="item.divider"
                        :key="index"
                        :inset="item.inset"
                        ></v-divider>

                        <v-list-item
                        v-else
                        :key="item.title"
                        link
                        >
                        <v-list-item-avatar>
                            <v-img :src="item.avatar"></v-img>
                        </v-list-item-avatar>

                        <v-list-item-content>
                            <v-list-item-title v-html="item.title"></v-list-item-title>
                            <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
                        </v-list-item-content>
                        </v-list-item>
                    </template>
                </v-list>
                 <v-btn small block>See all</v-btn>
            </v-menu>
            <br>
            <v-menu offset-y>
                <template v-slot:activator="{on, attrs}">
                    <span v-bind="attrs" v-on="on" style="cursor: pointer">
                        <v-avatar size="30"  class="mt-1">
                            <img aspect-ratio="30" src="https://randomuser.me/api/portraits/women/2.jpg">
                        </v-avatar>
                    </span>
                </template>
                
                <v-list width="250" class="py-0">
                    <v-list-item two-line>
                        <v-list-item-avatar>
                        <img aspect-ratio="40" src="https://randomuser.me/api/portraits/women/2.jpg">
                        </v-list-item-avatar>

                        <v-list-item-content>
                        <v-list-item-title>
                            Kang So Ra
                        </v-list-item-title>

                        <v-list-item-subtitle>
                            Logged In
                        </v-list-item-subtitle>
                        </v-list-item-content>
                    </v-list-item>
                    <v-divider/>
                    <v-list-item v-for="(menu, index) in menus" :key="index" link>
                        <v-list-item-icon>
                        <v-icon>{{menu.icon}}</v-icon>
                        </v-list-item-icon>
                        <v-list-content>
                        <v-list-item-title>
                            {{menu.title}}
                        </v-list-item-title>
                        </v-list-content>
                    </v-list-item>

                </v-list>
            </v-menu>
            
        </div>
    </v-navigation-drawer>
</template>

<script>
    export default {
        name: 'SideBar',
        data:()=>({
            selectItem: 0,
            drawer: null,
            items: [
                {icon: 'fas fa-plus'},
                {icon: 'fas fa-th-large'},
                {icon: 'fas fa-align-center'},
                {icon: 'fas fa-gitter'},
                {icon: 'fas fa-chart-line'}
            ],
            menus: [
                {title: "Profile", icon: "mdi-account"},
                {title: "Change password", icon: "mdi-key"},
                {title: "Setting", icon: "mdi-cog"},
                {title: "Logout", icon: "mdi-logout"}
            ],
            notifs: [
                {header: 'Today'},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Brunch this weekend',
                    subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                },
                {header: 'Yesterday'},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Brunch this weekend',
                    subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                }
            ],
            messages: [
                {header: 'Today'},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Brunch this weekend',
                    subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                },
                {header: 'Yesterday'},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Brunch this weekend',
                    subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend.`
                },
                { divider: true, inset: true},
                {
                    avatar: 'https://randomuser.me/api/portraits/women/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`
                }
            ],
        })
    }
</script>

<style scoped>
    .border{
        margin-left: 12px;
        margin-right: 12px;
        background: #4bb9e5;
        border-radius: 50%;
        text-decoration: none;
    }

    .v-list-item-group .v-list-item--active{
        color: #fff !important;
    }
</style>