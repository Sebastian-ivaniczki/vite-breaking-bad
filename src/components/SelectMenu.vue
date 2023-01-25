<script>
    export default {
        name: 'SelectMenu',
      data() {
        return{
            selected: ''
        }
      },
        props: {
            datas: Array
        },
        emits: [ 'change-value' ]

    }
</script>

<template>
    <div class="container d-flex justify-content-end">

        <select @change="$emit('change-value')" v-model="selected" class="form-select" aria-label="Default select example">
            <option selected value="">...</option>
            <option  v-for="data in datas" :value="data">{{ data }}</option>
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