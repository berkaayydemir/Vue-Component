<template>
  <div v-bind:id="'BaseDiv_' + propsData.ID" class="base-holder">
    <div class="info-container" v-bind:class="[headerClass, containerIconClass]">
      <div class="info-icon-container" v-bind:class="iconClass"></div>
      <div class="info-header-container" v-if="hasHeader">{{ propsData.HeaderText }}</div>
      <div class="info-content-container" v-bind:id="'info-content-container-' + propsData.ID">
        <div class="info-text-container">{{ propsData.Text }}</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ["propsData"],
    data() {
      let iconTypes = {
        yellow_i: {
          containerClassName: "yellow-bg",
          iconClassName: "info-icon-yellow",
        },
        blue_i: {
          containerClassName: "blue-bg",
          iconClassName: "info-icon-blue",
        },
        red_i: {
          containerClassName: "red-bg",
          iconClassName: "info-icon-red",
        },
        none: {
          containerClassName: "icon-none",
          iconClassName: "",
        }
      };
      return {
        newText: '',
        hasHeader: this.propsData.HeaderText == "" ? false : true,
        headerClass: this.propsData.HeaderText == "" ? "no-header" : "with-header",
        containerIconClass: iconTypes[this.propsData.Icon].containerClassName,
        iconClass: iconTypes[this.propsData.Icon].iconClassName,
      };
    }
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .info-container {
    width: 100%;
    outline: 0;
    position: relative;
    padding: 10px 20px;
    margin-top: 20px;
  }

  .info-container .info-icon-container {
    position: absolute;
    height: 32px;
    width: 32px;
    background-repeat: no-repeat;
    left: 25px;
    top: 15px;
  }

  .info-container .info-content-container {
    display: inline-block;
    vertical-align: top;
    position: relative;
    line-height: 21px;
    padding-bottom: 10px;
    padding-top: 10px;
    padding-left: 20px;
    width: 100%;
  }

  .info-container .info-content-container .info-text-container {
    text-align: left;
    font-size: 14px;
    word-wrap: break-word;
    word-break: normal;
    padding-left: 30px;
    padding-right: 20px;
  }

  .info-container .info-icon-container.info-icon-blue {
    top: 20px;
  }

  .info-container.blue-bg {
    background-color: #f1f9ff;
    color: #1c345c;
  }

  .info-container.red-bg {
    background-color: #fff3f3;
    color: #ff0000;
  }

  .info-container.yellow-bg {
    background-color: #f8f8c5;
    color: black;
  }

  .info-icon-red {
    background-image: url("../icons/red_exc.png");
  }

  .info-icon-yellow {
    background-image: url("../icons/yellow_exc.png");
  }

  .info-icon-blue {
    background-image: url("../icons/blue_exc_icon.png");
  }

  .info-container.with-header .info-header-container.icon-none {
    padding-left: unset;
  }
</style>