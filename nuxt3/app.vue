<template>
  <div class='app'>
    <FullCalendar :options=calendarOptions />
  </div>
</template>

<script setup lang="ts">
import {  ref } from "vue";
import FullCalendar from '@fullcalendar/vue3'
import interactionPlugin from '@fullcalendar/interaction'
import timeGridPlugin from '@fullcalendar/timegrid'
import  dayGridPlugin from "@fullcalendar/daygrid";
import multiMonthPlugin from "@fullcalendar/multimonth";

const calendarOptions =ref( {
  plugins: [interactionPlugin, timeGridPlugin ,dayGridPlugin,multiMonthPlugin],
  initialView: 'timeGridWeek',
  nowIndicator: true,
  headerToolbar:{
    letf:"prev,next",
    center:"title",
    right:"timeGridWeek,timeGridDay"
  },
  editable: true,
  initialEvents: [
    { title: 'nice event', start: new Date() }
  ]
})

</script>

<style scoped>
  .app {
    font-family: Arial, Helvetica Neue, Helvetica, sans-serif;
    font-size: 16px;
  }
</style>
