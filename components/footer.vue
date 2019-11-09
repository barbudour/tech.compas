<template>
    <div class="footer">
        <a href="#">
            <Logo/>
        </a>
    </div>
</template>

<script>
import Logo from "@/assets/svg/logo.svg?inline";
export default {
    components: {
        Logo
    },
}
</script>

<style lang="scss" scoped>
.footer {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 80px;
    background: #302E4A;
    z-index: 1;

    svg {
        path {
            fill: #ffffff;
        }
    }
}
</style>