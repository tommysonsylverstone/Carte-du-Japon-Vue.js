<template>
  <div class="container">
    <div class="map">Alternative content</div>
  </div>
</template>

<script>
import "jquery-mapael";
import $ from "jquery";
import "jquery-mapael/js/maps/japan";

export default {
  name: "JapanMap",
  data() {
    return {
      updatedOptions: {
        newPlots: {
          Tokyo: {
            plotsOn: "To",
            size: 4, //size of plot
            latitude: 35.709026,
            longitude: 139.731992,
            tooltip: { content: "Tokyo" }, //still dunno
            attrs: {
              //css
              cursor: "pointer",
            },
            attrsHover: {
              //css on hover
              "stroke-width": "0",
            },
            text: {
              //text that goes after the plot https://www.vincentbroute.fr/mapael/raphael-js-documentation/index.html#Element.attr
              content: "Tokyo",
              margin: 5,
              attrs: {
                "text-anchor": "start",
                "font-size": 10,
                fill: "#555555",
                opacity: 0,
                cursor: "pointer",
              },
              attrsHover: {
                opacity: 1,
                color: "red",
              },
            },
          },
          Nagasaki: {
            latitude: 32.75,
            longitude: 129.88333,
            tooltip: { content: "Nagasaki" },
            value: "unknown",
          },
        },
      },
    };
  },
  mounted() {
    $(".container").mapael({
      map: {
        name: "japan",
        zoom: {
          enabled: true,
        },
        defaultArea: {
          attrs: {
            "fill": "#555555",
            "stroke-width": "0",
          },
          attrsHover: {
            "fill": "#5E88BF"
          }
        }
      },
    });

    $(".container").trigger("update", this.updatedOptions);
  },
};
</script>

<style>
.map {
  background-color: #8BCAD9;
}
</style>