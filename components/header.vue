<template>
    <div class="header">
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
.header {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 80px;
    background: #ffffff;
    box-shadow: 0px 2px 20px rgba(48, 46, 74, 0.07);
    z-index: 1;
}
</style>