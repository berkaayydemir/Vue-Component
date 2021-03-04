<template>
  <div id="App">
    <div id="obiDiv">
      <div id="obiCanvasDiv">
        <component :is="component.type" v-for="(component,i) in components" :propsData="component.propsData" :key="i"></component>
      </div>
    </div>
  </div>
</template>

<script>
  import Info from "./components/Info.vue";
  import DataDisplayer from "./components/DataDisplayer.vue";

  export default {
    components: {
      Info,
      DataDisplayer
    },
    data() {
      return {
       components: [{
          type: "Info",
          propsData: {
            ID: "ExampleInfo",
            Text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
            Icon: "yellow_i",
            Visible: "true",
            HeaderText: ""
          },
        },
        {
          type: "Info",
          propsData: {
            ID: "ExampleInfo",
            Text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            Icon: "blue_i",
            Visible: "true",
            HeaderText: ""
          },
        },
        {
          type: "DataDisplayer",
          propsData: {
            ID: "ExampleDataDisplayer",
            LabelAndValue: [{Label:"Label1",Value:"Value1"},{Label:"Label2",Value:"Value2"}, {Label:"Label3",Value:"Value3"},{Label:"Label4",Value:"Value4"}],
            Visible: "true",
            HeaderText: "Lorem ipsum"
          },
        },
      ],
      // infoProps: {
      //       ID: "ExampleInfo",
      //       Text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ",
      //       Icon: "yellow_i",
      //       Visible: "true",
      //       HeaderText: ""
      //     }
      };
    },
  };
</script>

<style>
  #app {
    height: 100%;
    min-height: 100%;
    position: relative;
    width: 100%;
  }

  #App {
    width: 100%;
    height: 100%;
    color: black;
    background-color: #f2f2f2;
  }

  #obiCanvasDiv {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 20px 20px 20px 20px;
    max-width: 788px;
  }

  #obiDiv {
    background-color: white;
    color: black;
    margin-right: 50px;
    max-width: 788px;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }

  #obiDiv * {
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }

  html,
  body {
    height: 100%;
    margin: 0;
  }
</style>