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
                </div>
                <div class="social-links flex center">
                        <a target="_blank" :href="imdbLink" v-if="imdbLink !== '' ">
                            <svg width="50" height="24" viewBox="0 0 32 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <g clip-path="url(#clip0_4_243)">
                                <rect y="0.5" width="32" height="16" rx="2" fill="#F5C518"/>
                                <path d="M0.5 0.75C0.5 0.611929 0.388071 0.5 0.25 0.5C0.111929 0.5 0 0.611929 0 0.75C0 0.888071 0.111929 1 0.25 1C0.388071 1 0.5 0.888071 0.5 0.75Z" fill="#F5C518"/>
                                <path d="M4 13H6.5V4H4V13Z" fill="black"/>
                                <path d="M11.8363 4L11.2767 8.20423L10.9291 5.91751C10.8283 5.18505 10.7316 4.54588 10.6391 4H7.5V13H9.62082L9.62905 7.0569L10.5218 13H12.0317L12.8792 6.92589L12.8854 13H15V4H11.8363Z" fill="black"/>
                                <path d="M16 13V4H19.9023C20.7847 4 21.5 4.70997 21.5 5.5883V11.4117C21.5 12.2889 20.7858 13 19.9023 13H16ZM18.9161 5.61976C18.817 5.56617 18.6273 5.54036 18.3513 5.54036V11.4457C18.7156 11.4457 18.9398 11.3802 19.0239 11.2433C19.108 11.1083 19.1511 10.7431 19.1511 10.1436V6.65395C19.1511 6.24702 19.136 5.98699 19.108 5.87186C19.08 5.75673 19.0174 5.67336 18.9161 5.61976Z" fill="black"/>
                                <path d="M26.215 6.25343H26.3748C27.2724 6.25343 28 6.95634 28 7.82243V11.431C28 12.2975 27.2726 13 26.3748 13H26.215C25.6657 13 25.1801 12.7368 24.8859 12.3341L24.7419 12.8844H22.5V4H24.8922V6.89027C25.2012 6.50508 25.6776 6.25343 26.215 6.25343ZM25.7028 10.6421V8.50954C25.7028 8.15717 25.6802 7.92593 25.633 7.81948C25.5859 7.71304 25.3978 7.6447 25.2658 7.6447C25.1339 7.6447 24.9304 7.70024 24.8908 7.79383V8.50954V10.7104V11.4037C24.9361 11.5065 25.1301 11.5637 25.2658 11.5637C25.4016 11.5637 25.5991 11.5083 25.6406 11.4037C25.682 11.2991 25.7028 11.044 25.7028 10.6421Z" fill="black"/>
                                </g>
                                <defs>
                                <clipPath id="clip0_4_243">
                                <rect y="0.5" width="32" height="16" rx="2" fill="white"/>
                                </clipPath>
                                </defs>
                            </svg>
                        </a>
                        <a target="_blank" :href="instaLink" v-if="instaLink !== ''">
                            <img src="https://ik.imagekit.io/alexborecky/personal_web/600px-Instagram_icon_afIdZ7tkJ.png?ik-sdk-version=javascript-1.4.3&updatedAt=1660994810097" alt="" height="23px">
                        </a>
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
        props: ['thumbnail', 'filmTitle', 'filmLink', 'action', 'filmModal', 'actionLine', 'year', 'tagOne', 'tagTwo', 'tagThree', 'description', 'imdbLink', 'instaLink'],
        data () {
            return {
                filmModal: false,
                imdbLink: ''
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
        border-radius: 16px 16px 0 0;
    }
}

.film-window {
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
        border-radius: 16px 16px 0 0;
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
        .social-links {
            img {
                margin: 0 8px;
            }
            a {
                cursor: pointer;
                &:hover {
                    opacity: .64;
                }
            }
        }
    }
    @media (max-width: 550px) {
        max-height: 80vh;
        .thumbnail-section {
            .film-info {
                margin: 16px;
            }
        }
        .info-section {
            padding: 16px;
        }
    }
}

</style>