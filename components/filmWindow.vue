<template>
    <div class="modal-window">
        <div class="film-window flex">
            <div class="thumbnail-section flex column" :style="{backgroundImage: 'url('+ thumbnail +')'}">
                <div class="film-info">
                    <h3>{{filmTitle}}</h3>
                    <a target="_blank" :href="filmLink">{{actionLine}}</a>
                </div>
                <div class="cover"></div>
            </div>
            <div class="info-section">
                <div class="tag-bar flex">
                    <p><b>{{year}}</b></p>
                    <div class="tags flex">
                        <p class="tag">{{tagOne}}</p>
                    </div>
                    <div class="social-links">

                    </div>
                </div>
                <div class="description">
                    <p>{{description}}</p>
                </div>
                <div class="credits"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'filmWindow',
        props: ['thumbnail', 'filmTitle', 'filmLink', 'action', 'filmModal', 'actionLine', 'year', 'tagOne', 'tagTwo', 'tagThree', 'description'],
        data () {
            return {
                filmModal: false
            }
        }
    }
</script>

<style lang="scss" scoped>

.modal-window {
    padding: 0 !important;
    .cover {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        background: linear-gradient(180deg, rgba(0, 0, 0, 0) 50%, rgba(0, 0, 0, 0.8) 100%);
        transition: .3s ease-in;
    }
}

.film-window {
    border-radius: 8px;
    width: 100%;
    flex-flow: column;
    justify-content: flex-end;
    position: relative;
    transition: .3s ease-in;
    .thumbnail-section {
        position: relative;
        height: 40vh;
        background-size: cover;
        background-position: center;
        justify-content: flex-end;
        .film-info {
            z-index: 10006;
            margin: 32px 80px;
            h3 {
                font-size: 40px;
                font-weight: 600;
                margin: 16px 0;
            }
            a {
                padding: 8px 16px;
                background-color: white;
                color: black;
                border-radius: 8px;
                text-decoration: none;
                font-weight: 600;
                transition: .1s ease-in;
                border: 1px solid white;
                &:hover {
                    background-color: transparent;
                    border-radius: 8px;
                    border: solid 1px rgba($color: #fff, $alpha: .24);
                    color: white;
                }
            }
        }
    }
    .info-section {
        padding: 0px 80px 24px 80px;
        .description {
            p {
                line-height: 24px;
                opacity: .8;
            }
        }
        .tag-bar {
            p {
                font-size: 16px;
                b {
                    font-weight: 600;
                }
            }
            .tags {
                margin-left: 40px;
                .tag {
                    opacity: .64;
                    font-weight: 400;
                }
            }
        }
    }
}

</style>