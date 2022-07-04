<template>
  <div class="booking-units">
    <h2>Cimso <br /><span>Booking Unit information</span></h2>

    <div class="card-display" v-if="payload">
      <div
        class="unit-card"
        v-for="unitBooking in payload"
        :key="unitBooking['Booking Unit ID']"
      >
        <div class="unit-type-information">
          <h3>Unit Type</h3>
          <div class="unit-top">
            <div class="unit-info-left">
              <p>
                <span class="highlight">Unit ID:</span>
                {{ unitBooking["Unit Type ID"] }}
              </p>
              <p>
                <span class="highlight">Unit Code: </span
                >{{ unitBooking["Unit Type Code"] }}
              </p>
              <p>
                <span class="highlight">Decription:</span>
                {{ unitBooking["Unit Type Description"] }}
              </p>
              <p>
                <span class="highlight">Category:</span>
                {{ unitBooking["Unit Type Category"] }}
              </p>
            </div>
            <div class="unit-info-right">
              <p>
                <span class="highlight">Max Occupants: </span
                >{{ unitBooking["Maximum Occupants"] }}
              </p>
              <p>
                <span class="highlight">Max Adults: </span
                >{{ unitBooking["Maximum Adults"] }}
              </p>
              <p>
                <span class="highlight">Max Children:</span>
                {{ unitBooking["Maximum Children"] }}
              </p>
            </div>
          </div>
          <div class="description">
            <p>
              <span class="highlight">Marketing Description:</span>
              <br /><br />{{ unitBooking["Marketing Description"] }}
            </p>
          </div>
          <div class="location-count">
            <p>
              <span class="highlight">Locationg ID:</span
              >{{ unitBooking["Location ID"] }}
            </p>
            <p>
              <span class="highlight">Unit Count:</span
              >{{ unitBooking["Unit Count"] }}
            </p>
          </div>
          <p class="img-uid">
            <span class="highlight">Image UIDs:</span
            >{{ unitBooking["Unit Type Image UIDs"] }}
          </p>
        </div>
        <div class="booking-request">
          <h3>Booking Information</h3>
          <div class="booking-disp">
            <div class="booking-left">
              <p>
                <span class="highlight">Booking Unit Number:</span>
                {{ unitBooking["Booking Unit Number"] }}
              </p>
              <p>
                <span class="highlight">Unit Type ID:</span>
                {{ unitBooking["Unit Type ID"] }}
              </p>
            </div>
            <div class="booking-right">
              <p>
                <span class="highlight">Booking Unit ID:</span>
                {{ unitBooking["Booking Unit ID"] }}
              </p>
              <p>
                <span class="highlight">Booking Unit Name:</span>
                {{ unitBooking["Booking Unit Name"] }}
              </p>
            </div>
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
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      payload: [],
    };
  },
  mounted() {
    let unitApi =
      "https://apitest.cimsoweb.com/api/innterchange/unit_type_info_request";
    let bookingApi =
      "https://apitest.cimsoweb.com/api/innterchange/get_booking_units_request";

    const requestUnit = axios.get(unitApi);
    const requestBooking = axios.get(bookingApi);

    axios
      .all([requestUnit, requestBooking])
      .then(
        axios.spread((...responses) => {
          const unitsTypes = responses[0].data.payload["Unit Types"];
          const bookingUnits = responses[1].data.payload["Booking Units"];
          // join the api
          this.payload = bookingUnits.map((bookingInfo) => {
            const unitType = unitsTypes.find(
              (unitInfo) =>
                unitInfo["Unit Type ID"] === bookingInfo["Unit Type ID"]
            );
            return { ...bookingInfo, ...unitType };
          });
        })
      )
      .catch((errors) => {
        console.error(errors);
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
  border-color: transparent rgb(255, 252, 252) transparent rgb(246, 240, 240);
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
  color: #f8f4f4;
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
.unit-type-information {
  border-bottom: 2px solid white;
}
.booking-units {
  margin-top: 150px;
}
h2 {
  padding: 1rem;
  font-size: 1.9rem;
  font-weight: 900;
  text-align: center;
  color: rgb(190, 215, 57);
}
h3 {
  color: rgb(190, 215, 57);
}
h2 span {
  font-size: 1.4rem;
  font-weight: 300;
  color: #999;
}
.card-display {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  justify-content: center;
}
.unit-card {
  width: 500px;
  border: 2px solid white;
  padding: 30px;
}
.unit-card p {
  color: white;
  font-family: "Courier New", Courier, monospace;
}
.unit-top {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-evenly;
}
.unit-info-left {
  text-align: start;
}
.unit-info-right {
  text-align: start;
}
.highlight {
  color: #999;
  font-weight: bolder;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  font-size: 20px;
}
.description {
  text-align: start;
  padding-left: 30px;
}
.location-count {
  display: flex;
  justify-content: space-evenly;
  gap: 60px;
}
.img-uid {
  padding-left: 23px;
  padding-bottom: 20px;
}
.booking-disp {
  display: flex;
  justify-content: space-between;
  gap: 15px;
}
.booking-right {
  text-align: start;
}
.booking-left {
  text-align: start;
}
</style>
