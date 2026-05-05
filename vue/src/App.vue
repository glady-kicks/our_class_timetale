<template>
  <div>
    <h1>L3SOD B Timetable</h1>

    <table>
      <thead>
        <tr>
          <th>Day / Time</th>
          <th v-for="(col, i) in headers" :key="i" :class="getClass(col)">
            {{ col }}
          </th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="day in timetable" :key="day.name">
          <td>{{ day.name }}</td>
          <td
            v-for="(lesson, i) in day.lessons"
            :key="i"
            :class="getClass(headers[i])"
          >
            {{ lesson }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        "08:00","09:00","10:00","11:00",
        "Break",
        "11:30","12:30",
        "Lunch",
        "14:00","15:00",
        "Break",
        "15:30","16:30"
      ],

      timetable: [
        {
          name: "Mo",
          lessons: [
            "UIUX","UIUX","DJF","DGV",
            "Break",
            "MATH","DJF",
            "Lunch",
            "UIUX","GD",
            "Break",
            "DGV","DJF"
          ]
        },
        {
          name: "Tu",
          lessons: [
            "DJF","DJF","DJF","DJF",
            "Break",
            "CL","UIUX",
            "Lunch",
            "DGV","VC Prac",
            "Break",
            "UIUX","DJF"
          ]
        },
        {
          name: "We",
          lessons: [
            "VC","UIUX",
            "DGV","DJF",
            "Break",
            "UIUX","DGV",
            "Lunch",
            "DJF","MATH",
            "Break",
            "UIUX","DGV"
          ]
        },
        {
          name: "Th",
          lessons: [
            "UIUX","DGV",
            "DJF","DJF",
            "Break",
            "PHY","UIUX",
            "Lunch",
            "DGV","DJF",
            "Break",
            "UIUX","DGV"
          ]
        },
        {
          name: "Fr",
          lessons: [
            "DGV","UIUX",
            "FR","DJF",
            "Break",
            "UIUX","DGV",
            "Lunch",
            "DJF","UIUX",
            "Break",
            "DGV","DJF"
          ]
        }
      ]
    };
  },

  methods: {
    getClass(item) {
      if (item === "Break") return "break";
      if (item === "Lunch") return "lunch";
      return "";
    }
  }
};
</script>

<style>
body {
  font-family: Arial;
}

h1 {
  text-align: center;
}

table {
  border-collapse: collapse;
  width: 100%;
}

th, td {
  border: 1px solid rgb(228, 219, 219);
  padding: 6px;
  text-align: center;
}

th {
  background-color: lightblue;
}

.break {
  background-color: rgb(15, 194, 226);
}

.lunch {
  background-color: rgb(10, 169, 180);
  color: white;
}
</style>