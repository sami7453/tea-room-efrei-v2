<template>
    <form class="custom-form">
        <section class="custom-form__fields-section">
            <FieldComponent
                @field-change="onFieldChange" 
                v-for="(field,index) in data.fields" 
                :key="index"
                :data="field"
            />
        </section>
        <section class="custom-form__buttons-section">
            <ButtonComponent 
                v-for="(btn,index) in data.buttons"
                :key="index"
                :data="btn"
            />
        </section>
    </form>
</template>
<script lang="ts" setup>
import type FormInterface from "../interfaces/FormInterface";
import ButtonComponent from "./ButtonComponent.vue";
import FieldComponent from "./FieldComponent.vue"

interface FormComponentProperties {
    data: FormInterface
}

defineProps<FormComponentProperties>()

const onFieldChange = ({ id, val }:{ id: string, val: string }) => {
    console.log('id', id)
    console.log('val', val)
}


</script>