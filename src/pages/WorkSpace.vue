<template>
  <div class="row">
    <div class="col-12">
      <card :title="table1.title" :subTitle="table1.subTitle">
        <div slot="raw-content" class="table-responsive">
          <paper-table :data="table1.data" :columns="table1.columns">
          </paper-table>
        </div>
      </card>
    </div>

    <div class="col-12">
      <card class="card-plain" :title="table2.title" :sub-title="table2.subTitle">
        <div class="table-full-width table-responsive">
          <paper-table
            type="hover"
            
            
            :data="table2.data"
            :columns="table2.columns"
          >
          </paper-table>
        </div>
      </card>
    </div>
  </div>
</template>
<script>
import { PaperTable } from "@/components";
const tableColumns = ["Id", "Title", "Author", "Keywords", "Score", "Action"];
const tableData = [
  {
    id: 1,
    author: "Dakota Rice",
    title: "The Secret They Don't Want You to Know!",
    keywords: "AI",
    Action: "Oud-Turnhout",
    url: "https://www.inc.com/matthew-jones/the-ultimate-secret-about-life-that-no-one-wants-you-to-know.html",
  },
  {
    id: 2,
    author: "Minerva Hooper",
    title: "Rules Not To Follow About BIDEN",
    keywords: "Biden",
    Action: "Siai-Waas",
    url: "https://www.whitehouse.gov/briefing-room/statements-releases/2021/12/02/fact-sheet-president-biden-announces-new-actions-to-protect-americans-against-the-delta-and-omicron-variants-as-we-battle-covid-19-this-winter/",
  },
  {
    id: 3,
    author: "Sage Rodriguez",
    title: "3 Mistakes In AI That Make You Look Dumb",
    keywords: "AI",
    Action: "Baileux",
    url: "https://www.google.com",
  },
  {
    id: 4,
    author: "Philip Chaney",
    title: "Top 10 Tips To Grow Your BIDEN",
    keywords: "BIDEN, Korea, South",
    Action: "Overland Park",
  },
  {
    id: 5,
    author: "Doris Greene",
    title: "Guaranteed No Stress AI",
    keywords: "AI, Stress",
    Action: "Feldkirchen in Kärnten",
    url: "https://www.google.com",
  },
];
const tableData2 = [
  {
    id: 1,
    author: "Dakota Rice",
    title: "The Secret They Don't Want You to Know!",
    keywords: "AI",
    Action: "Oud-Turnhout",
    url: "https://www.google.com",
    score: 0,
    isRecord: true
  },
  {
    id: 2,
    author: "Minerva Hooper",
    title: "Rules Not To Follow About BIDEN",
    keywords: "Biden",
    Action: "Sinaai-Waas",
    url: "https://www.google.com",
    score: 4,
  },
  {
    id: 3,
    author: "Sage Rodriguez",
    title: "3 Mistakes In AI That Make You Look Dumb",
    keywords: "AI",
    Action: "Baileux",
    url: "https://www.google.com",
    score: 1,
  },
  {
    id: 4,
    author: "Philip Chaney",
    title: "Top 10 Tips To Grow Your BIDEN",
    keywords: "BIDEN, Korea, South",
    Action: "Overland Park",
    score: 5,
  },
  {
    id: 5,
    author: "Doris Greene",
    title: "Guaranteed No Stress AI",
    keywords: "AI, Stress",
    Action: "Feldkirchen in Kärnten",
    url: "https://www.google.com",
    score: 2,
  },
];

export default {
  components: {
    PaperTable,
  },
  data() {
    return {
      table1: {
        title: "News",
        subTitle: "news need to be classified",
        columns: [...tableColumns],
        data: [...tableData],
      },
      table2: {
        title: "Records",
        subTitle: "The news you have been rated",
        columns: [...tableColumns],
        data: [...tableData2],
      },
    };
  },
};
</script>
<style>
</style>
