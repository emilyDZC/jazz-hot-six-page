<template>
    <div class="event-row">
        {{ date }} - {{ venue }} ({{ players }})
    </div>
</template>

<script>
export default {
    name: 'EventRow',
    props: {
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