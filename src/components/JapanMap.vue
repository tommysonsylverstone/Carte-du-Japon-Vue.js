<template>
  <div class="container">
    <div class="map"></div>
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
            fill: "#5ba4ff",
            stroke: "#99c7ff",
            cursor: "pointer",
          },
          attrsHover: {
            animDuration: 0,
          },
          eventHandlers: {
            click: function (e, id) {
              if (id) {
                $(".modal").remove();
                var x = e.clientX + scrollX;
                var y = e.clientY + scrollY;
                $(".map").append(
                  "<div class='modal " +
                    id +
                    "' style='left:" +
                    x +
                    "px; top:" +
                    y +
                    "px'>Test id</div>"
                );
              }
            },
          },
        },
      },
      areas: {
        Hokkaido: {
          href: "",
          tooltip: { content: "<span>Hokkaido</span>" },
        },
        Okinawa: {
          value: 2,
          href: "",
        },
        Shimane: {
          value: 3,
          href: "",
        },
        Okayama: {
          value: 4,
          href: "",
        },
        Yamaguchi: {
          value: 5,
          href: "",
        },
        Osaka: {
          value: 6,
          href: "",
        },
        Hyogo: {
          value: 7,
          href: "",
        },
        Iwate: {
          value: 8,
          href: "",
        },
        Ibaraki: {
          value: 9,
          href: "",
        },
        Fukushima: {
          value: 10,
          href: "",
        },
        Chiba: {
          value: 11,
          href: "",
        },
        Tottori: {
          value: 12,
          href: "",
        },
        Wakayama: {
          value: 13,
          href: "",
        },
        Mie: {
          value: 14,
          href: "",
        },
        Kanagawa: {
          value: 15,
          href: "",
        },
        Shizuoka: {
          value: 16,
          href: "",
        },
        Hiroshima: {
          value: 17,
          href: "",
        },
        Nigata: {
          value: 18,
          href: "",
        },
        Aichi: {
          value: 19,
          href: "",
        },
        Kyoto: {
          value: 20,
          href: "",
        },
        Aomori: {
          value: 21,
          href: "",
        },
        Nagano: {
          value: 22,
          href: "",
        },
        Ishikawa: {
          value: 23,
          href: "",
        },
        Toyama: {
          value: 24,
          href: "",
        },
        Fukui: {
          value: 25,
          href: "",
        },
        Akita: {
          value: 26,
          href: "",
        },
        Kagawa: {
          value: 27,
          href: "",
        },
        Kochi: {
          value: 28,
          href: "",
        },
        Ehime: {
          value: 29,
          href: "",
        },
        Tokushima: {
          value: 30,
          href: "",
        },
        Kumamota: {
          value: 31,
          href: "",
        },
        Kagoshima: {
          value: 32,
          href: "",
        },
        Nagasaki: {
          value: 33,
          href: "",
        },
        Fukuoka: {
          value: 34,
          href: "",
        },
        Saga: {
          value: 35,
          href: "",
        },
        Miyazaki: {
          value: 36,
          href: "",
        },
        Oita: {
          value: 37,
          href: "",
        },
        Gifu: {
          value: 38,
          href: "",
        },
        Tochigi: {
          value: 39,
          href: "",
        },
        Gunma: {
          value: 40,
          href: "",
        },
        Saitama: {
          value: 41,
          href: "",
        },
        Yamanashi: {
          value: 42,
          href: "",
        },
        Shiga: {
          value: 43,
          href: "",
        },
        Tokyo: {
          value: 44,
          href: "",
          tooltip: { content: "Test" },
        },
        Nara: {
          value: 45,
          href: "",
        },
        Yamagate: {
          value: 46,
          href: "",
        },
        Miyagi: {
          value: 47,
          href: "",
        },
      },
    });

    $(".container").trigger("update", this.updatedOptions);
  },
};
</script>

<style>
.map {
  background-color: #8bcad9;
}
.mapael .mapTooltip {
  position: absolute;
  background-color: #474c4b;
  moz-opacity: 0.7;
  opacity: 0.7;
  filter: alpha(opacity=70);
  border-radius: 10px;
  padding: 10px;
  z-index: 1000;
  max-width: 200px;
  display: none;
  color: #fff;
}
.modal {
  position: absolute;
}
</style>