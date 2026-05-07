# App.vue

```vue
<template>
  <div class="container">

    <h1>🎓 L3SOD B  Timetable</h1>

    <!-- DAYS -->
    <div class="days-container">

      <div
        v-for="day in timetable"
        :key="day.name"
        class="day-card"
        @click="openDay(day)"
      >
        {{ day.name }}
      </div>

    </div>

    <!-- ACTIVITIES -->
    <div v-if="selectedDay" class="activity-box">

      <h2>
        {{ selectedDay.name }} Activities
      </h2>

      <div
        v-for="(lesson, index) in selectedDay.lessons"
        :key="index"
        class="activity-link"
      >
        🔗 {{ headers[index] }} → {{ lesson }}
      </div>

    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {

      selectedDay: null,

      headers: [
        "08:00",
        "09:00",
        "10:00",
        "11:00",
        "Break",
        "11:30",
        "12:30",
        "Lunch",
        "14:00",
        "15:00",
        "Break",
        "15:30",
        "16:30"
      ],

      timetable: [

        {
          name: "Monday",
          lessons: [
            "UIUX",
            "UIUX",
            "DJF",
            "DGV",
            "Break",
            "MATH",
            "DJF",
            "Lunch",
            "UIUX",
            "GD",
            "Break",
            "DGV",
            "DJF"
          ]
        },

        {
          name: "Tuesday",
          lessons: [
            "DJF",
            "DJF",
            "DJF",
            "DJF",
            "Break",
            "CL",
            "UIUX",
            "Lunch",
            "DGV",
            "VC Prac",
            "Break",
            "UIUX",
            "DJF"
          ]
        },

        {
          name: "Wednesday",
          lessons: [
            "VC",
            "UIUX",
            "DGV",
            "DJF",
            "Break",
            "UIUX",
            "DGV",
            "Lunch",
            "DJF",
            "MATH",
            "Break",
            "UIUX",
            "DGV"
          ]
        },

        {
          name: "Thursday",
          lessons: [
            "UIUX",
            "DGV",
            "DJF",
            "DJF",
            "Break",
            "PHY",
            "UIUX",
            "Lunch",
            "DGV",
            "DJF",
            "Break",
            "UIUX",
            "DGV"
          ]
        },

        {
          name: "Friday",
          lessons: [
            "DGV",
            "UIUX",
            "FR",
            "DJF",
            "Break",
            "UIUX",
            "DGV",
            "Lunch",
            "DJF",
            "UIUX",
            "Break",
            "DGV",
            "DJF"
          ]
        }

      ]
    };
  },

  methods: {

    openDay(day) {
      this.selectedDay = day;
    }

  }
};
</script>

<style>

body{
  margin:0;
  font-family:Arial, Helvetica, sans-serif;
  background:#0f172a;
}

.container{
  padding:40px;
  text-align:center;
}

h1{
  color:white;
  margin-bottom:40px;
  font-size:40px;
}

/* 3D DAY CARDS */

.days-container{
  display:flex;
  justify-content:center;
  gap:25px;
  flex-wrap:wrap;
}

.day-card{
  width:180px;
  height:120px;
  background:linear-gradient(145deg,#2563eb,#06b6d4);
  color:white;
  font-size:24px;
  font-weight:bold;
  display:flex;
  align-items:center;
  justify-content:center;
  border-radius:20px;
  cursor:pointer;
  transform:perspective(1000px) rotateX(10deg);
  box-shadow:
    0 10px 20px rgba(0,0,0,0.4),
    inset 0 2px 5px rgba(255,255,255,0.3);
  transition:0.3s;
}

.day-card:hover{
  transform:perspective(1000px) rotateX(0deg) scale(1.08);
}

/* ACTIVITIES */

.activity-box{
  margin-top:40px;
  background:white;
  padding:25px;
  border-radius:20px;
  max-width:700px;
  margin-left:auto;
  margin-right:auto;
  box-shadow:0 10px 25px rgba(0,0,0,0.4);
}

.activity-box h2{
  color:#2563eb;
  margin-bottom:20px;
}

.activity-link{
  background:#eff6ff;
  margin:10px 0;
  padding:15px;
  border-radius:12px;
  font-weight:bold;
  color:#1e293b;
  transition:0.3s;
  cursor:pointer;
}

.activity-link:hover{
  background:#2563eb;
  color:white;
  transform:translateX(8px);
}

</style>
```
