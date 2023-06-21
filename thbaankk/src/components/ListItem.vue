<template>
    <div class="col-md-4">
        <div class="card" :style="{'background-color': (card.age > 30 ? 'yellow': 'orange') }">
            <div class="card-body">
                <h6 class="card-title">{{ card.firstname + ' ' + card.lastname }}</h6>
                <p class="card-text">อายุ: {{ card.age }} <br/> จังหวัด: {{ card.city }} <br/> แนวเพลง: {{ card.style }}</p>
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
    