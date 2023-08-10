<template>
    <div class="event-row">
        <s v-if="past">
            {{ date }} - {{ venue }} ({{ players }})
        </s>
        <template v-else>
            {{ date }} - {{ venue }} ({{ players }})
        </template>
    </div>
</template>

<script>
export default {
    name: 'EventRow',
    props: {
        past: Boolean,
        date: String,
        venue: String,
        players: String
    }
}
</script>

<style scoped>
    .event-row {
        color: bisque;
    }
</style>