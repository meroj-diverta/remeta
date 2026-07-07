<template>
    <div>
        <div v-for="n in response.details.ext_1" :key="n.slag">
            <img :src="n.ext_1.url" width="400">
            <div>id: {{ n.ext_1.id }}</div>
            <div>desc: {{ n.ext_1.desc }}</div>
            <div>url_org: {{ n.ext_1.url_org }}</div>
            <img :src="n.ext_2.url" width="400">
            <div>id: {{ n.ext_2.id }}</div>
            <div>desc: {{ n.ext_2.desc }}</div>
            <div>url_org: {{ n.ext_2.url_org }}</div>
        </div>
    </div>
</template>

<script setup>
const config = useRuntimeConfig();

const { data: response } = await useFetch(
    `${config.public.apiBase}/rcms-api/2/services/3`,
    {
        credentials: 'include',
    }
);
</script>