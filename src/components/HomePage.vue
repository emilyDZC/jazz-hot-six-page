<template>
    <div class="homepage">
        <div class="full-screen-view">
            <div v-if="!isMobile" class="left">
                <img class="pic" src="../assets/martin1.jpeg" width="200" />
                <img class="pic" src="../assets/emily1.jpeg" width="200" />
                <img class="pic" src="../assets/jazz-hot-six-1.jpeg" width="400" />
            </div>
            <div class="middle">
                <img src="../assets/jazz-hot-six.jpeg" width="300"/>
                <!-- <h1 class="title">Upcoming gigs</h1> -->

                <p class="yellow-text">Come and see us at the <a href="https://dorothypax.com/">Dorothy Pax</a> in Sheffield on the first Tuesday of every month!!</p>
                <p class="yellow-text smaller">Free entry, 8pm start.</p>
                <!-- <EventRow v-for="event in upcomingEvents" :date="formatDate(event.date)" :venue="event.venue" :players="event.players" :key="event.date"/> -->

                <!-- <h1 class="title">Previous gigs</h1> -->
                <!-- <EventRow v-for="event in pastEvents" :date="formatDate(event.date)" :venue="event.venue" :players="event.players" :key="event.date"/> -->

            </div>
            <div v-if="!isMobile" class="right">
                <img class="pic" src="../assets/kate1.jpeg" width="200" />
                <img class="pic" src="../assets/andrew1.jpeg" width="200" />
            </div>
        </div>
        <div v-if="isMobile">
            <h1 class="title">Gallery</h1>
            <img class="pic-small" src="../assets/martin1.jpeg" height="100" />
            <img class="pic-small" src="../assets/kate1.jpeg" height="100" />
            <img class="pic-small" src="../assets/emily1.jpeg" height="100" />
            <img class="pic-small" src="../assets/andrew1.jpeg" height="100" />
            <img class="pic-small" src="../assets/jazz-hot-six-1.jpeg" height="100" />
        </div>
    </div>
</template>

<script>
// import EventRow from "./EventRow.vue"

export default {
    name: 'HelloWorld',
    // components: { EventRow },
    data() {
        return {
            events: [
                {
                    date: "2023-06-06",
                    venue: "Dorothy Pax",
                    players: "no Shez",
                    past: true
                },
                {
                    date: "2023-07-04",
                    venue: "Dorothy Pax",
                    players: "all",
                    past: true
                },
                {
                    date: "2023-07-23",
                    venue: "Pax in the Park (Tramlines Weekend) - afternoon",
                    players: "all",
                    past: true
                },
                {
                    date: "2023-09-05",
                    venue: "Dorothy Pax",
                    players: "all",
                    past: false
                },
                {
                    date: "2023-10-07",
                    venue: "TBC",
                    players: "all",
                    past: false
                },
            ],
            upcomingEvents: [],
            pastEvents: []
        }
    },
    created() {
        this.upcomingEvents = this.getUpcomingEvents();
        this.pastEvents = this.getPastEvents();
    },
    computed: {
        isMobile() {
            return screen.width <= 375;
        },
    },
    methods: {
        getUpcomingEvents() {
            return this.events.filter(event => {
                let eventDate = new Date(event.date);
                let today = new Date();
                return eventDate >= today
            })
        },
        getPastEvents() {
             return this.events.filter(event => {
                let eventDate = new Date(event.date);
                let today = new Date();
                return eventDate <= today
            }).reverse()
        },

        formatDate(date) {
            let eventDate = new Date(date);
            return eventDate.toLocaleDateString('en-GB', {weekday: 'long', month: 'long', day: "numeric"})
        }
    }
}
</script>

<style>
    body {
        background-color: rgb(76, 90, 104);
    }

    .homepage {
        font-weight: 700;
    }

    .full-screen-view {
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .title {
        color: rgb(250, 174, 51);
    }

    .left, .right {
        width: 30vw;
        display: flex;
        flex-direction: column;
        align-items: center;
        flex: 5;
    }

    .middle {
        flex: 5;
    }

    img {
        max-width: 100%;
    }

    .pic {
        border: 5px solid beige;
        margin: 5px;
    }

    .pic-small {
        border: 2px solid beige;
        margin: 5px;
    }

    .yellow-text {
        color: rgb(250, 174, 51);
        font-size: 1.7rem;
    }

    .smaller {
        font-size: 1.3rem;
    }

    a, a:hover {
        text-decoration: none;
        color: rgb(250, 174, 51);
    }

    a:hover {
        text-decoration: underline;
    }
</style>