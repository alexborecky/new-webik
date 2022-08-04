<template>
    <nuxt-link :to="pageSection" class="title-links">
        <p>{{sectionTitle}}</p>
        <div class="line">
            <div class="inner-line"></div>
        </div>
    </nuxt-link>
</template>

<script>
    export default {
        name: 'heroLink',
        props: ['pageSection', 'sectionTitle']
    }
</script>

<style lang="scss" scoped>

a {
    text-decoration: none;
    p {
        font-size: 24px;
        font-weight: 500;
        letter-spacing: 2px;
        text-decoration: none;
        color: rgba($color: #fff, $alpha: .72);
        transition: .3s ease-in;
    }
}

.line {
    background-color: rgba($color: #fff, $alpha: .24);
    position: relative;
    .inner-line {
        position: absolute;
        width: 0%;
        height: 0%;
        background-color: rgba($color: #fff, $alpha: .88);
        transition: .3s ease-in;
        bottom: 0;
        right: 0;
    }
}

a:hover {
    p {
        color: rgba($color: #fff, $alpha: 1);
    }
    .line {
        .inner-line {
            width: 100%;
            height: 100%;
        }
    }
}

</style> 