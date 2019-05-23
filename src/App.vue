<template>
    <div>
        <VueTextPencentage
            text="afeafe"
            fill="#ff1234"
            unit="m"
            unitColor="#ff3456"
        ></VueTextPencentage>
    </div>
</template>

<script type="text/javascript">
    import VueTextPencentage from './myPlugin/components/text2pencentage'
    export default {
        name: 'vue-text-pencentage',
        components: {VueTextPencentage},
        data () {
            return {};
        }
    }
</script>
