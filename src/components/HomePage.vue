<template>
    <div class="homepage">
        <div class="left">
            <img class="pic" src="../assets/martin1.jpeg" width="200" />
            <img class="pic" src="../assets/emily1.jpeg" width="200" />
            <img class="pic" src="../assets/jazz-hot-six-1.jpeg" width="400" />
        </div>
        <div class="middle">
            <img src="../assets/jazz-hot-six.jpeg" width="300"/>
            <h1 class="title">Gig List</h1>

            <EventRow v-for="event in events" :date="event.date" :venue="event.venue" :players="event.players" :past="event.past" :key="event.date"/>
        </div>
        <div class="right">
            <img class="pic" src="../assets/kate1.jpeg" width="200" />
            <img class="pic" src="../assets/andrew1.jpeg" width="200" />
        </div>

        <br/>
        <br/>
        <br/>
        <br/>
    </div>
</template>

<script>
import EventRow from "./EventRow.vue"

export default {
    name: 'HelloWorld',
    components: { EventRow },
    data() {
        return {
            events: [
                {
                    date: "Tuesday 6th June",
                    venue: "Dorothy Pax",
                    players: "no Shez",
                    past: true
                },
                {
                    date: "Tuesday 4th July",
                    venue: "Dorothy Pax",
                    players: "all",
                    past: true
                },
                {
                    date: "Sunday 23rd July",
                    venue: "Pax in the Park (Tramlines Weekend) - afternoon",
                    players: "all",
                    past: true
                },
                {
                    date: "Tuesday 5th September",
                    venue: "Dorothy Pax",
                    players: "all",
                    past: false
                },
                {
                    date: "Saturday 7th October",
                    venue: "TBC",
                    players: "all",
                    past: false
                },
            ]
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
    }

    img {
        max-width: 100%;
    }

    .pic {
        border: 5px solid beige;
        margin: 5px;
    }
</style>