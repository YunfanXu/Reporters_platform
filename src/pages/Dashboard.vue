<template>
  <div>
    <!--Stats cards-->
    <div class="row">
      <div
        class="col-md-6 col-xl-3"
        v-for="stats in statsCards"
        :key="stats.title"
      >
        <stats-card>
          <div
            class="icon-big text-center"
            :class="`icon-${stats.type}`"
            slot="header"
          >
            <i :class="stats.icon"></i>
          </div>
          <div class="numbers" slot="content">
            <p>{{ stats.title }}</p>
            {{ stats.value }}
          </div>
          <div class="stats" slot="footer">
            <i :class="stats.footerIcon"></i> {{ stats.footerText }}
          </div>
        </stats-card>
      </div>
    </div>

    <!--Charts-->
    <div class="row">
      <div class="col-12">
        <chart-card
          title="The number of people you helped"
          sub-title="Last Week"
          :chart-data="usersChart.data"
          :chart-options="usersChart.options"
        >
          <span slot="footer">
            <i class="ti-reload"></i> Updated 3 minutes ago
          </span>
          <div slot="legend">
            <i class="fa fa-circle text-danger"></i> Last Week
            <i class="fa fa-circle text-warning"></i> Your Best Record
            <i class="fa fa-circle text-info"></i> Best contributor in the world
          </div>
        </chart-card>
      </div>

      <div class="col-md-6 col-12">
        <chart-card
          title="Reports Statistics"
          sub-title="Last month performance"
          :chart-data="preferencesChart.data"
          chart-type="Pie"
        >
          <span slot="footer"> <i class="ti-timer"></i> Since from Oct. 1</span>
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> Accepted
            <i class="fa fa-circle text-danger"></i> Pending
            <i class="fa fa-circle text-warning"></i> Rejected
          </div>
        </chart-card>
      </div>

      <div class="col-md-6 col-12">
        <chart-card
          title="Contributions"
          sub-title="Reports you submitted during the past year"
          :chart-data="activityChart.data"
          :chart-options="activityChart.options"
        >
          <span slot="footer">
            <i class="ti-check"></i> Data information certified
          </span>
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> Your contribution
            <i class="fa fa-circle text-warning"></i> Best contributor
          </div>
        </chart-card>
      </div>

      <!-- <div class="col-md-12 col-12">
        <chart-card
          title="Without WAF Services VS. Scrapers"
          chart-type="Bar"
          sub-title="Record the number of crawlered times before rejected"
          :chart-data="WAFChart.data"
          :chart-options="WAFChart.options"
        >
          <span slot="footer">
            <i class="ti-crown"></i> From Group 5: Anti-Scraping --development
            and analysis
          </span>
          <div slot="legend">
            <i class="fa fa-circle text-info"></i> Scrapy
            <i class="fa fa-circle text-warning"></i> Puppeteer
            <i class="fa fa-circle text-danger"></i> Selenium
          </div>
        </chart-card>
      </div> -->
    </div>
  </div>
</template>
<script>
import { StatsCard, ChartCard } from "@/components/index";
import Chartist from "chartist";

const getXindex = new Array(100).fill(0).map((val, index) => {
  if ((index + 1) % 10 === 0) {
    return index + 1;
  } else {
    return "";
  }
});
const getYindex = new Array(100).fill(48);
const getPuppeteer = new Array(100)
  .fill(0)
  .map((val, index) => (index > 58 ? 0 : 47));
const getScrapy = new Array(100)
  .fill(0)
  .map((val, index) => (index > 11 ? 0 : 47));
const getSelenium = new Array(100)
  .fill(0)
  .map((val, index) => (index > 38 ? 0 : 47));

export default {
  components: {
    StatsCard,
    ChartCard,
  },
  /**
   * Chart data used to render stats, charts. Should be replaced with server data
   */
  data() {
    return {
      statsCards: [
        {
          type: "success",
          icon: "ti-medall",
          title: "Scores",
          value: "430",
          footerText: "Updated now",
          footerIcon: "ti-reload",
        },
        {
          type: "warning",
          icon: "ti-cup",
          title: "Global Ranking",
          value: "1,345",
          footerText: "Last day",
          footerIcon: "ti-calendar",
        },
        {
          type: "info",
          icon: "ti-shield",
          title: "Reported",
          value: "423",
          footerText: "In the last hour",
          footerIcon: "ti-timer",
        },
        {
          type: "danger",
          icon: "ti-heart",
          title: "Be liked",
          value: "+255",
          footerText: "Updated now",
          footerIcon: "ti-reload",
        },
      ],
      usersChart: {
        data: {
          labels: [
            "",
            "Monday",
            "Tuesday",
            "Wensday",
            "Thursday",
            "Friday",
            "Saturday",
            "Sunday",
            "",
          ],
          series: [
            [0, 180, 320, 459, 505, 627, 778, 907],
            [0, 65, 143, 283, 393, 487, 578, 667],
            [0, 80, 120, 259, 305, 327, 378, 407],
          ],
        },
        options: {
          low: 0,
          high: 1000,
          showArea: true,
          height: "245px",
          axisX: {
            showGrid: false,
          },
          lineSmooth: Chartist.Interpolation.simple({
            divisor: 3,
          }),
          showLine: true,
          showPoint: false,
        },
      },
      activityChart: {
        data: {
          labels: [
            "Jan",
            "Feb",
            "Mar",
            "Apr",
            "Mai",
            "Jun",
            "Jul",
            "Aug",
            "Sep",
            "Oct",
            "Nov",
            "Dec",
          ],
          series: [
            [110, 193, 280, 320, 103, 253, 320, 364, 298, 110, 136, 295],
            [542, 543, 520, 680, 653, 753, 526, 434, 568, 610, 756, 895],
          ],
        },
        options: {
          low: 0,
          high: 1000,
          seriesBarDistance: 10,
          axisX: {
            showGrid: false,
          },
          height: "245px",
        },
      },
      preferencesChart: {
        data: {
          labels: ["82%", "12%", "6%"],
          series: [82, 12, 6],
        },
        options: {},
      },

      WAFChart: {
        // data: {
        //   labels: ["CloudFlare", " Tencent Cloud", "Barracuda"],
        //   series: [
        //     [8, 12, 22],
        //     [12, 28, 47],
        //     [18, 36, 38],
        //   ],
        // },
        data: {
          labels: ["szszet.com", "szszet.online", "szszet.one"],
          series: [
            [100, 100, 100],
            [100, 100, 100],
            [100, 100, 100],
          ],
        },
        options: {
          low: 0,
          high: 110,
          seriesBarDistance: 20,
          showPoint: false,
          showArea: true,
          height: "280px",
        },
      },
    };
  },
};
</script>
<style>
</style>
