<template>
    <div class="album-card">
        <img :src="poster" :alt="title" class="img-fluid" />
        <h5>{{ title }}</h5>
        <div class="description">
            <span class="author">{{ author }}</span>
            <span class="year">{{ year }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: "CardComponents",
    props: ["poster", "title", "author", "year"],
};
</script>

<style scoped lang="scss">
@import "../../assets/style/variabili.scss";
 
    .album-card {
        color: white;
        background-color: $colorCard;
        text-align: center;
        padding: 15px;
        margin: 15px;
        height: 370px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        h5 {
            font-weight: 600;
            text-transform: uppercase;
            font-size: 1.1rem;
            margin: 10px 0;
        }

        .author, .year {
            display: block;
            color: #cacac6;
        }
    }
</style>