<template>
  <v-container class="fill-height" fluid>
    <v-row align="center" justify="center">
      <v-col class="text-center">
        <div class="content">
          <v-row align="center" justify="center">
            <!-- <v-breadcrumbs :items="items">
              <template v-slot:divider>
                <v-icon>mdi-chevron-right</v-icon>
              </template>
            </v-breadcrumbs>-->
            {{Vote}}
            <v-row align="center" justify="center">
              <v-col cols="9">
                <div class="layout-article">
                  <h3 class="subject">{{Vote[0].activityName}}</h3>
                  <v-col cols="12">
                    <div>
                      活動類別：票選
                      <br />主辦單位：校務資訊組
                      <br />發稿日期：107年10月30日
                      <br />聯 絡 人：賈希謙
                      <br />聯絡電話：0911111111
                      <br />
                      活動說明：{{Vote[0].activityDescription}}
                    </div>
                  </v-col>
                  <div class="text-center">
                    <v-btn rounded color="warning" dark>
                      <router-link :to="{path:'/getTicket'}">進入投票</router-link>
                    </v-btn>
                  </div>
                </div>
              </v-col>
            </v-row>
          </v-row>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { mapState, mapActions } from "vuex";
export default {
  data() {
    return {};
  },
  computed: {
    ...mapState({
      Vote: state => state.vote.ActivityDetail
    })
  },
  methods: {
    ...mapActions(["GET_ACTIVITY_DETAIL"])
  },
  created() {
    // this.$route.params.id
    this.GET_ACTIVITY_DETAIL(1);
  }
};
</script>

<style>
.layout-article {
  background: #e9f0fe;
  border: 1px solid #bdcef2;
  color: #3b5fad;
  word-break: break-all;
}

.layout-article .subject {
  line-height: 1.5;
  color: #3b5fad;
  background-color: #ffffff;
  border-radius: 0 1000px 1000px 0;
  padding: 0.5rem 2rem;
  width: calc(100% - 4rem);
  box-sizing: border-box;
}
</style>