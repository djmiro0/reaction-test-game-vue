<template>
    <div>
        <h2>Reaction time: {{ (reactionTime / 1000).toFixed(3) }}s</h2>
        <h3>Rating: {{ reactionRating }}</h3>
    </div>
</template>

<script>
export default {
    name: "Results",
    props: ["reactionTime"],
    computed: {
        reactionRating() {
            const time = this.reactionTime;

            if (time <= 200) return "🧠 Incredible";
            else if (time <= 300) return "⚡ Fast";
            else if (time <= 500) return "🙂 Average";
            else if (time <= 800) return "🐢 Slow";
            else return "😴 Very Slow";
        }
    }
}
</script>

<style></style>
