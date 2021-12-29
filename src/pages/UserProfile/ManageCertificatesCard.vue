<template>
  <card class="card" title="Update Your Certificates">
    <div>
      <ul class="list-unstyled team-files">
        <li>
          <div v-for="file in files" :key="file.name">
            <div class="row">
              <div class="col-9">
                <h4>{{ file.name }}</h4>
              </div>
              <div class="col-3"  v-bind:style="statusContainer">
                <h4 :class="getStatusClass(file.status)">
                  {{ file.status }}
                </h4>
              </div>
            </div>

            <div class="row">
              <div class="col-8">
                File Names: {{file.fileNames.join("; ")}}
              </div>
              <div class="col-4">
                <span>
                  <v-file-input multiple label="File input"></v-file-input>
                </span>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </card>
</template>
<script>
export default {
  data() {
    return {
      statusContainer:{
        display:"flex",
        alignItems:"center"
      },
      files: [
        {
          name: "Education Certificate",
          status: "Qualified",
          fileNames: ["Master Degree", "PHd Degree"],
        },
        {
          name: "Skills Certificates",
          status: "Qualified",
          fileNames: ["Python", "AI", "Machine Learning", "Deep Learning"],
        },
        {
          name: "Email Certificate",
          status: "None",
          fileNames: [""],
        },
        {
          name: "Academic Certificates",
          status: "Qualified",
          fileNames: ["Google schoolar", "IEEE committee member"],
        },
        {
          name: "Organization Certificates",
          status: "Pending",
          fileNames: ["New York University"],
        },
      ],
    };
  },
  methods: {
    getStatusClass(status) {
      switch (status) {
        case "Qualified":
          return "text-success";
        case "Pending":
          return "text-warning";
        case "None":
          return "text-danger";
        default:
          return "text-success";
      }
    },
  },
};
</script>
<style>
</style>
