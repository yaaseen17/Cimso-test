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
    <h1>Loading...</h1>
    <div class="loader">
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
      <span class="loader-block"></span>
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
.loader {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 7.33333em;
  height: 7.33333em;
  margin-left: -3.66667em;
  margin-top: -3.66667em;
}
.loader-block {
  position: absolute;
  top: 0;
  left: 0;
  display: inline-block;
  opacity: 0;
  width: 2em;
  height: 2em;
  background: #2d2764;
  -webkit-animation: show 0.88s step-end infinite alternate,
    pulse 0.88s linear infinite alternate;
  animation: show 0.88s step-end infinite alternate,
    pulse 0.88s linear infinite alternate;
}
.loader-block:nth-child(1) {
  -moz-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -webkit-transform: translate(0, 0);
  transform: translate(0, 0);
  -webkit-animation-delay: 0.065s;
  animation-delay: 0.065s;
}
.loader-block:nth-child(2) {
  -moz-transform: translate(2.66667em, 0);
  -ms-transform: translate(2.66667em, 0);
  -webkit-transform: translate(2.66667em, 0);
  transform: translate(2.66667em, 0);
  -webkit-animation-delay: 0.13s;
  animation-delay: 0.13s;
}
.loader-block:nth-child(3) {
  -moz-transform: translate(5.33333em, 0);
  -ms-transform: translate(5.33333em, 0);
  -webkit-transform: translate(5.33333em, 0);
  transform: translate(5.33333em, 0);
  -webkit-animation-delay: 0.195s;
  animation-delay: 0.195s;
}
.loader-block:nth-child(4) {
  -moz-transform: translate(0, 2.66667em);
  -ms-transform: translate(0, 2.66667em);
  -webkit-transform: translate(0, 2.66667em);
  transform: translate(0, 2.66667em);
  -webkit-animation-delay: 0.325s;
  animation-delay: 0.325s;
}
.loader-block:nth-child(5) {
  -moz-transform: translate(2.66667em, 2.66667em);
  -ms-transform: translate(2.66667em, 2.66667em);
  -webkit-transform: translate(2.66667em, 2.66667em);
  transform: translate(2.66667em, 2.66667em);
  -webkit-animation-delay: 0.13s;
  animation-delay: 0.13s;
}
.loader-block:nth-child(6) {
  -moz-transform: translate(5.33333em, 2.66667em);
  -ms-transform: translate(5.33333em, 2.66667em);
  -webkit-transform: translate(5.33333em, 2.66667em);
  transform: translate(5.33333em, 2.66667em);
  -webkit-animation-delay: 0.455s;
  animation-delay: 0.455s;
}
.loader-block:nth-child(7) {
  -moz-transform: translate(0, 5.33333em);
  -ms-transform: translate(0, 5.33333em);
  -webkit-transform: translate(0, 5.33333em);
  transform: translate(0, 5.33333em);
  -webkit-animation-delay: 0.39s;
  animation-delay: 0.39s;
}
.loader-block:nth-child(8) {
  -moz-transform: translate(2.66667em, 5.33333em);
  -ms-transform: translate(2.66667em, 5.33333em);
  -webkit-transform: translate(2.66667em, 5.33333em);
  transform: translate(2.66667em, 5.33333em);
  -webkit-animation-delay: 0.26s;
  animation-delay: 0.26s;
}
.loader-block:nth-child(9) {
  -moz-transform: translate(5.33333em, 5.33333em);
  -ms-transform: translate(5.33333em, 5.33333em);
  -webkit-transform: translate(5.33333em, 5.33333em);
  transform: translate(5.33333em, 5.33333em);
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
