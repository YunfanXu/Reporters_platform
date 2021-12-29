<template>
  <survey :survey="survey" />
</template>

<script>
import * as Survey from "survey-vue";

import "bootstrap/dist/css/bootstrap.css";
import "survey-vue/survey.css";
// import "./index.css";

Survey.StylesManager.applyTheme("survey-vue");

export default {
  name: "survey-component",
  data() {
    const json = {
      questions: [
        {
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "God’s",
          title: "Do you agree with God’s Importance in Life?",
          minRateDescription: "(Nothing important)",
          maxRateDescription: "(Very importand)",
        },
        {
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "abortion",
          title: "Do you agree with ABORTION?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },
        {
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Euthanasia",
          title: "Do you agree with Euthanasia?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },
        {
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Suicide",
          title: "Do you agree with Suicide?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Prostitution",
          title: "Do you agree with Prostitution?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Smoking marijuana or hashish",
          title: "Do you agree with Smoking marijuana or hashish?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Artificial insemination",
          title: "Do you agree with Artificial insemination?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Extramarital relations",
          title: "Do you agree with Extramarital relations?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Intercourse with occasional partners",
          title: "Do you agree with Intercourse with occasional partners?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Homosexuality",
          title: "Do you agree with Homosexuality?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Immigration",
          title: "Do you agree with Immigration?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Death Penalty",
          title: "Do you agree with? Death Penalty",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },{
          isRequired: true,
          rateMin: 0,
          rateMax: 10,
          type: "rating",
          name: "Unemployed",
          title: "Do you agree with Unemployed?",
          minRateDescription: "Always",
          maxRateDescription: "Never",
        },
      ],
    };
    const survey = new Survey.Model(json);

    return {
      survey: survey,
    };
  },
};
</script>

<style scoped>
</style>
