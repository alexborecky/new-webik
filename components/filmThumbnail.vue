<template>
    <div class="film-thumbnail flex" :style="{backgroundImage: 'url('+ thumbnail +')'}">
        <div class="cover"></div>
        <div class="film-toolbar">
            <h3>{{filmTitle}}</h3>
            <div class="info-bar flex">
                <a :href="filmLink"><img src="https://ik.imagekit.io/alexborecky/personal_web/Play_KB_xemX-n.png?ik-sdk-version=javascript-1.4.3&updatedAt=1659622281663" alt="">{{status}}</a>
                <a><img src="https://ik.imagekit.io/alexborecky/personal_web/info_ExZUzVQCZ.png?ik-sdk-version=javascript-1.4.3&updatedAt=1659622281661" alt=""></a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'filmThumbnail',
        props: ['thumbnail', 'filmTitle', 'filmLink', 'status', 'action'],
    }
</script>

<style lang="scss" scoped>

.film-thumbnail {
    border-radius: 8px;
    height: 350px;
    width: 100%;
    background-size: cover;
    background-position: center;
    flex-flow: column;
    justify-content: flex-end;
    position: relative;
    transition: .3s ease-in;
    .film-toolbar {
        margin: 32px;
        z-index: 100;
        .info-bar {
            margin-top: 8px;
            width: 100%;
            justify-content: space-between;
        }
        a:nth-child(1) {
            display: flex;
            align-items: center;
            font-size: 16px;
            font-weight: 500;
            letter-spacing: 2px;
            img {
                margin-right: 8px;
                height: 16px;
                width: 16px;
            }
        }
        a:nth-child(2) {
            img {
                height: 24px;
                width: 24px;
            }
        }
    }
    &:hover {
        transform: translateY(-8px);
    }
    .cover {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        background: linear-gradient(180deg, rgba(0, 0, 0, 0) 50%, rgba(0, 0, 0, 0.8) 100%);
        transition: .3s ease-in;
    }
}

</style>