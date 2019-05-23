<template>
    <div class="text_2_pencentage" :id="id">
        <svg :style="{width: '100%', height: calcluteHeight}" :viewBox="'0,0,' + svgWidth + ',' + svgHieght" style="line-height: 1;">
            <text
                id="metric"
                x="50%"
                y="50%"
                dy="7"
                text-anchor="middle"
                style="font-size: 20px; line-height: 1;"
                :style="{fill: fill}">
                <tspan>{{text}}</tspan>
                <tspan style="font-size: 16px;" :style="{fill: unitColor}">{{unit}}</tspan>
            </text>
        </svg>
    </div>
</template>

<script type="text/javascript">
    export default {
        name: 'vue-text-pencentage',
        props: {
            id: {
                type: String,
                default: 'text2pencentage'
            },
            height: {
                type: String,
                default: '400'
            },
            width: {
                type: String,
                default: 'auto'
            },
            text: {
                type: String,
                default: 'Test text'
            },
            fill: {
                type: String,
                default: '#333'
            },
            unit: {
                type: String,
                default: ''
            },
            unitColor: {
                type: String,
                default: '#123456'
            },
            percentage: {
                type: [Number, String],
                default: 0.8
            }
        },
        watch: {
            height () {
                this.initMounted();
            },
            width () {
                this.initMounted();
            },
            text () {
                this.initMounted();
            },
            fill () {
                this.initMounted();
            },
            unit () {
                this.initMounted();
            },
            unitColor () {
                this.initMounted();
            },
            percentage () {
                this.initMounted();
            }
        },
        data () {
            return {
                svgWidth: 0,
                svgHieght: 0
            };
        },
        computed: {
            calcluteHeight () {
                let height = parseFloat(this.height);
                return (this.height == 'auto' ? 'auto' : height + 'px');
            }
        },
        mounted () {
            this.initMounted();
        },
        methods: {
            initMounted () {
                setTimeout(() => {
                    this.drawSvg();
                }, 400);
            },
            drawSvg () {
                let box = document.getElementById(this.id);
                // if (!box) return;
                let boxW = box.offsetWidth;
                let boxH = parseInt(this.height);

                let bool = /(%)$/i.test(this.percentage);

                let per = bool ? parseFloat(this.percentage) / 100 : parseFloat(this.percentage);

                if (isNaN(per)) return;

                let smallW = Math.ceil(document.getElementById('metric').getComputedTextLength());
                let svgPer = (per + smallW / boxW * (1 - per));
                let svgWidth = smallW / (per + smallW / boxW * (1 - per));

                this.svgWidth = svgWidth < smallW ? smallW : svgWidth;
                this.svgHieght = 22 / (per + 22 / 400 * (1 - per));
            }
        }
    }
</script>
