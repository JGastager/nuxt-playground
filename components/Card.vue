<template>
    <div ref="card" class="card">
        <div class="inner">
            <slot></slot>
        </div>
        <div class="halo"></div>
        <div class="halo-init"></div>
    </div>
</template>
<script setup>
const card = ref(null);

onMounted(() => {
    card.value.addEventListener("mousemove", (e) => {
        const halo = card.value.querySelector(".halo");
        const haloInit = card.value.querySelector(".halo-init");
        const rec = haloInit.getBoundingClientRect();
        halo.style.opacity = "1";

        halo.animate(
            [
                {
                    transform: `translate(${(e.clientX - rec.left) - (rec.width / 2)}px,${(e.clientY - rec.top) - (rec.height / 2)}px)`
                }
            ],
            {
                duration: 300,
                fill: "forwards"
            }
        );
    });
});

</script>

<style lang="scss">
    .card {
        background-color: rgba(100, 100, 100, 0.5);
        border-radius: 10px;
        // box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        // border: 1px solid rgba(50, 50, 50, 0.5);
        padding: 1px;
        cursor: pointer;
        color: white;
        position: relative;
        overflow: hidden;
        transition: all 0.3s;

        .halo {
            filter: blur(40px);
            position: absolute;
            z-index: -1;
            top: 0;
            opacity: 0;
            left: 0;
            width: 250px;
            height: 250px;
            border-radius: 50%;
            background: rgb(255, 255, 255, 0.5);
            transition: all 0.3s;
        }

        .halo-init {
            display: hidden;
            position: absolute;
            z-index: -1;
            top: 0;
            left: 0;
            width: 200px;
            height: 200px;
            border-radius: 50%;
        }

        .inner {
            border-radius: 9px;
            padding: 1rem;
            background: rgba(25, 25, 25, 0.1);
            backdrop-filter: blur(80px);
            transition: all 0.3s;
        }

        &:hover > .inner {
            background: rgba(25, 25, 25, 0.1);
            backdrop-filter: blur(80px);
        }
    }
</style>