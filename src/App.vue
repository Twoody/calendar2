<template>
  <div id="app">
    <vue-cal
      :time-cell-height="18"
      style="height: 350px"
      default-view="week"
      :disable-views="['years', 'year', 'month']"
      :events="events"
      :time-from="8 * 60"
      :time-to="20 * 60"
      :time-step="1 * 60"
      :selected-date="'2018-11-21'"
      hide-weekends
     >
      <template v-slot:time-cell="{ hours }">
        <div :class="{ line: true }">
          {{ hours }}
        </div>
      </template>

      <template v-slot:event-renderer="{ event, view }">
        <span class="foo">{{ event.title }}</span>
      </template>

      <template v-slot:cell-content="{ cell, view, events }">
        <span class="vuecal__cell-date">{{ "meatz" }}</span>
      </template>

    </vue-cal>
  </div>
</template>

<script>
import VueCal from 'vue-cal'
import 'vue-cal/dist/vuecal.css'
export default {
  name: 'app',
  components:
  {
    VueCal
  },
  data: function () {
    return {
    events: [
      {
        start: '2018-11-21 00:00',
        end: '2018-11-21 12:00',
        title: 'Need to go shopping',
        content: '<i class="v-icon material-icons">shopping_cart</i>',
        class: 'leisure'
      },
      {
        start: '2018-11-21 13:00',
        end: '2018-11-21 15:00',
        title: 'Golf with John',
        content: '<i class="v-icon material-icons">golf_course</i>',
        class: 'sport'
      },
      {
        start: '2018-11-22 00:00',
        end: '2018-11-22 23:59',
        title: 'Dad\'s birthday!',
        content: '<i class="v-icon material-icons">cake</i>',
        class: 'sport'
      }
    ]
  }},
  created: function (){
  },//end created
  mounted () {
  },

  methods:
  {
  }//end methods
}
</script>

<style lang="scss">
  .vuecal {
    box-shadow: none;
  }
  .vuecal__time-cell {
    .line {
    /* margin-left: 15px; */
    }
    .line:before{
      margin-left:55px;
    /* border-top: none !important; */
    }
  }
</style>
