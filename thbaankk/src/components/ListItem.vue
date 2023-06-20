<template>
    <div class="col-md-4">
        <div class="card" :style="{'background-color': (card.age > 30 ? 'yellow': 'orange') }">
            <div class="card-body">
                <h5 class="card-title">{{ card.firstname + ' ' + card.lastname }}</h5>
                <p class="card-text">age: {{ card.age }} <br/> city: {{ card.city }} <br/> style: {{ card.style }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        card: {
            type: Object
        }
    }
}
</script>
    