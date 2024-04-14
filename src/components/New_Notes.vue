<template>
    <div class="hello">
        <h1> {{ oneNote }}</h1>
        <h1> {{ id }}</h1>
        <h1> {{ result }}</h1>
    </div>
</template>

<script>
export default {
    // в наш пропсы собираем условмия  тип, требование, и по умолчанию, если не будет дефолт будет по умолчанию надапись.
    props: {
        oneNote: {
            type: String,
            required: true,
            default: 'нету значения',
            // валидатор чтото рповеряет пока знаю что есть на зачем не понятно.
            validator(value) {
                console.log(value)
                return true

            }
        },
        id: Number,
        result: String,
    },
    data() {
        return {}
    },
}
</script>
