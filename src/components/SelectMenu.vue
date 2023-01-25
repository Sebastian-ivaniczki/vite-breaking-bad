<script>
    export default {
        name: 'SelectMenu',
        data() {
            return 
        }, 
        props: {
            datas: Array
        } 
    }
</script>

<template>
    <div class="container d-flex justify-content-end">

        <select class="form-select" aria-label="Default select example">
            <option selected value="">...</option>
            <option v-for="data in datas" :value="data">{{ data }}</option>
        </select>
    </div>
</template>

<style scoped lang="scss">
.container{
    .form-select{
            width: 15%;
        }

}

</style>