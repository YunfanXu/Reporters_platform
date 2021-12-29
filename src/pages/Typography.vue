<template>
  <div class="row">
    <div class="col-md-12">
      <card>
        <template slot="header">
          <h4 class="card-title">
            Questionnaire for measuring the left-right political scale
          </h4>
          <p class="card-category">
            Cited from
            <a href="https://www.mdpi.com/2304-6775/9/2/23"
              >The Influence of Political Ideology on Fake News Belief: The
              Portuguese Case</a
            >
          </p>
        </template>
        <div>
          <h3>Please answer the questions as below:</h3>
          <div class="content">
            <survey-component />
          </div>
        </div>
      </card>
    </div>
  </div>
</template>
<script>
import SurveyComponent from "../components/SurveyComponent.vue";

export default {
  components: { SurveyComponent },
};
</script>
<style>
</style>
