<script>
import FullCalendar from "@fullcalendar/vue3";
import dayGridPlugin from "@fullcalendar/daygrid";
import timeGridPlugin from "@fullcalendar/timegrid";
import listPlugin from "@fullcalendar/list";
import interactionPlugin from "@fullcalendar/interaction";

export default {
  components: {
    FullCalendar, // make the <FullCalendar> tag available
  },
  data() {
    return {
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin, timeGridPlugin, listPlugin],
        defaultView: "dayGridMonth",
        initialView: "dayGridMonth",
        dateClick: this.handleDateClick,
        headerToolbar: {
          center: "title",
          left: "prev,next",
          right: "dayGridMonth,timeGridWeek,timeGridDay,listWeek",
        },
        weekend: false,
        events: "https://fullcalendar.io/api/demo-feeds/events.json",
        contentHeight: 760,
        aspectRatio: 0.5,
        
      },
    };
  },
  methods: {
    handleDateClick: function (arg) {
      alert("date click! " + arg.dateStr);
    },
  },
};
</script>
<template>
  <div class="w-full h-full px-5 mt-4">
    <FullCalendar :options="calendarOptions" />
  </div>
</template>

<style>
.fc .fc-toolbar.fc-header-toolbar {
  display: block;
}

.fc-button {
  border-radius: 5px;
  font-size: 14px;
  padding: 5px 10px;
  justify-items: center;
  /* display: flex */
}

.fc .fc-toolbar-title {
    font-size: 1.75em;
    margin: 0px;
    text-align: center;
}

.fc .fc-button-group {
    display: inline-flex;
    position: relative;
    vertical-align: middle;
    display: flex;
}
</style>
