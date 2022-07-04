<template>
  <h2>Cimso <br /><span>Booking Unit information</span></h2>
  <div v-if="payload">
    <div v-for="data in payload" :key="data">
      <div v-for="payload in data" :key="payload">
        <div>
          <table>
            <tr>
              <th>Unit Type IDs</th>
              <th>Booking Unit IDs</th>
              <th>Booking Unit ID</th>
              <th>Booking Unit Name</th>
              <th>Booking Unit Number</th>
              <th>Unit Type ID</th>
            </tr>
            <tr v-for="payloads in payload" :key="payloads">
              <td class="numbers">{{ payloads["Unit Type ID"] }}</td>
              <td class="numbers">{{ payloads["Booking Unit ID"] }}</td>
              <td class="numbers">{{ payloads["Booking Unit ID"] }}</td>
              <td class="numbers">{{ payloads["Booking Unit Name"] }}</td>
              <td class="numbers">{{ payloads["Booking Unit Number"] }}</td>
              <td class="numbers">{{ payloads["Unit Type ID"] }}</td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </div>
  <div v-else>
    <div class="loading-container">
      <div class="loading"></div>
      <div id="loading-text">loading</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      payload: null,
    };
  },
  mounted() {
    axios
      .get(
        "https://apitest.cimsoweb.com/api/innterchange/get_booking_units_request"
      )
      .then((res) => {
        this.payload = res.data;
        let bookings = "Booking Unit ID";
        console.log(this.payload["Booking Units"]);
      })
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>
<style scoped>
@keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-moz-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-webkit-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-o-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-moz-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-webkit-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@-o-keyframes rotate-loading {
  0% {
    transform: rotate(0deg);
    -ms-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
    -ms-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
  }
}

@keyframes loading-text-opacity {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-moz-keyframes loading-text-opacity {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-webkit-keyframes loading-text-opacity {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-o-keyframes loading-text-opacity {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
.loading-container,
.loading {
  height: 100px;
  position: relative;
  width: 100px;
  border-radius: 100%;
}

.loading-container {
  margin: 40px auto;
}

.loading {
  border: 2px solid transparent;
  border-color: transparent rgb(0, 0, 0) transparent rgb(0, 0, 0);
  -moz-animation: rotate-loading 1.5s linear 0s infinite normal;
  -moz-transform-origin: 50% 50%;
  -o-animation: rotate-loading 1.5s linear 0s infinite normal;
  -o-transform-origin: 50% 50%;
  -webkit-animation: rotate-loading 1.5s linear 0s infinite normal;
  -webkit-transform-origin: 50% 50%;
  animation: rotate-loading 1.5s linear 0s infinite normal;
  transform-origin: 50% 50%;
}

.loading-container:hover .loading {
  border-color: transparent #e45635 transparent #e45635;
}
.loading-container:hover .loading,
.loading-container .loading {
  -webkit-transition: all 0.5s ease-in-out;
  -moz-transition: all 0.5s ease-in-out;
  -ms-transition: all 0.5s ease-in-out;
  -o-transition: all 0.5s ease-in-out;
  transition: all 0.5s ease-in-out;
}

#loading-text {
  -moz-animation: loading-text-opacity 2s linear 0s infinite normal;
  -o-animation: loading-text-opacity 2s linear 0s infinite normal;
  -webkit-animation: loading-text-opacity 2s linear 0s infinite normal;
  animation: loading-text-opacity 2s linear 0s infinite normal;
  color: #000000;
  font-family: "Helvetica Neue, " Helvetica ", " "arial";
  font-size: 10px;
  font-weight: bold;
  margin-top: 45px;
  opacity: 0;
  position: absolute;
  text-align: center;
  text-transform: uppercase;
  top: 0;
  width: 100px;
}

@-webkit-keyframes pulse {
  from,
  40% {
    background: #2d2764;
  }
  to {
    background: #dadada;
  }
}
@-webkit-keyframes show {
  from,
  40% {
    opacity: 0;
  }
  41%,
  to {
    opacity: 1;
  }
}
@keyframes pulse {
  from,
  40% {
    background: #2d2764;
  }
  to {
    background: #dadada;
  }
}
@keyframes show {
  from,
  40% {
    opacity: 0;
  }
  41%,
  to {
    opacity: 1;
  }
}

h2 {
  padding: 1rem;
  font-size: 1.5rem;
  font-weight: 900;
  text-align: center;
  color: #999;
}

h2 span {
  font-size: 1.25rem;
  font-weight: 300;
  color: #a52a2a;
}

table {
  display: grid;
  line-height: 1.25;
  border: 0;
  border-collapse: collapse;
}

tr {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  text-align: center;
}

tr:nth-of-type(odd) {
  background-color: #e5e5e5;
}

th {
  font-weight: 700;
  background-color: #f2f2f2;
  color: #666;
}

th,
td {
  padding: 0.5rem 0.1rem;
  border: 1px solid #bfbfbf;
  border-collapse: collapse;
  border-spacing: 0;
}

/* This will affect only Chrome browsers 29+
	* See: http://browserhacks.com/
	* Hack because 'hyphens: auto;' is supported in Chrome only on Android & Mac 
	* and word-break 'overrides' hyphens in Firefox
	*/
.selector:not(*:root),
th,
td {
  word-wrap: break-word;
  overflow-wrap: break-word;
  word-break: break-all;
}

td:first-of-type {
  padding-left: 0.25rem;
  font-weight: 300;
  text-align: left;
  color: darkslategray;
}

/* Breaking the numbers! */
.numbers {
  word-break: break-word;
}
</style>
