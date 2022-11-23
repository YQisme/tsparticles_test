<template>
    <Particles id="tsparticles" :options="options" :particlesInit="particlesInit" />
</template>
<script lang="ts">
import Particles from "vue3-particles";

import type { Engine } from "tsparticles-engine";
import { loadSlim } from "tsparticles-slim"
export default {
    data() {
        return {
            options: {
                fullScreen: {
                    enable: true,
                    zIndex: -1,
                },
                interactivity: {
                    events: {
                        onclick: {
                            enable: true,
                            mode: "push",
                        },
                        onHover: {
                            enable: true,
                            mode: "repulse",
                        },
                    },
                    modes: {
                        push: {
                            quantity: 10
                        },
                        repulse: {
                            distance: 100,
                        },
                    },
                },

                particles: {

                    links: {
                        distance: 100,
                        enable: true,
                        color: "#000",
                    },
                    move: {
                        enable: true,
                        speed: { min: 1, max: 5 },
                    },
                    opacity: {
                        value: { min: 0.3, max: 0.7 }
                    },
                    size: {
                        value: { min: 1, max: 3 }
                    },
                },
            },
        };
    },
    methods: {
        async particlesInit(engine: Engine) {
            await loadSlim(engine);
        }
    },
};

</script>