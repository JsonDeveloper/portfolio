<template>
    <section class="contacts">
        <div class="contacts__content">
            <h1 v-text="t('contacts.title')" />
            <ul class="contacts__list">
                <!-- Email -->
                <li class="contacts__item">
                    <a class="contacts__link" href="mailto:kriakiku@icloud.com" target="_blank">
                        <h4 class="contacts__label">
                            <span class="contacts__icon" role="img">📮</span>
                            Email
                        </h4>
                        <p class="contacts__value">kriakiku@icloud.com</p>
                    </a>
                </li>
                <!-- Telegram -->
                <li class="contacts__item">
                    <a class="contacts__link" href="https://t.me/kriakiku" target="_blank">
                        <h4 class="contacts__label">
                            <img class="contacts__icon" src="/icons/telegram.svg" alt="Telegram Logo" width="18" height="18" />
                            Telegram
                        </h4>
                        <p class="contacts__value">https://t.me/kriakiku</p>
                    </a>
                </li>
                <!-- LinkedIn -->
                <li class="contacts__item">
                    <a class="contacts__link" href="https://www.linkedin.com/in/kriakiku/" target="_blank">
                        <h4 class="contacts__label">
                            <img class="contacts__icon" src="/icons/linkedin.svg" alt="LinkedIn Logo" width="18" height="18" />
                            LinkedIn
                        </h4>
                        <p class="contacts__value">https://www.linkedin.com/in/kriakiku</p>
                    </a>
                </li>
                <!-- HackerOne -->
                <li class="contacts__item">
                    <a class="contacts__link" href="https://hackerone.com/kriakiku" target="_blank">
                        <h4 class="contacts__label">
                            <img class="contacts__icon" src="/icons/hackerone.svg" alt="HackerOne Logo" width="18" height="18" />
                            HackerOne
                        </h4>
                        <p class="contacts__value">https://hackerone.com/kriakiku</p>
                    </a>
                </li>
                <!-- Github -->
                <li class="contacts__item">
                    <a class="contacts__link" href="https://github.com/kriakiku" target="_blank">
                        <h4 class="contacts__label">
                            <img class="contacts__icon" src="/icons/github.svg" alt="Github Logo" width="18" height="18" />
                            Github
                        </h4>
                        <p class="contacts__value">https://github.com/kriakiku</p>
                    </a>
                </li>
                <!-- Facebook -->
                <li class="contacts__item">
                    <a class="contacts__link" href="https://www.facebook.com/kriakiku/" target="_blank">
                        <h4 class="contacts__label">
                            <img class="contacts__icon" src="/icons/facebook.svg" alt="Facebook Logo" width="18" height="18" />
                            Facebook
                        </h4>
                        <p class="contacts__value">https://www.facebook.com/kriakiku</p>
                    </a>
                </li>
            </ul>
        </div>
        <div class="contacts__art">
            <UiLottie v-if="sticker" :content="sticker" :width="250" :height="250" :loop="false" />
        </div>
    </section>
</template>

<script setup>
import sticker from '~/assets/stickers/contacts.json'
// const { data: sticker } = await useFetch('/stickers/contacts.json')

const { t } = useI18n()

useMeta({ 
    link: [
        { rel: 'preload', href: '/contacts-overlay.jpg', as: 'image', type: 'image/jpg' }
    ],
    title: t('contacts.title')
})
</script>

<style lang="scss">
    .contacts {
        display: flex;
        margin: 42px 0;

        @media screen and (max-width: 628px) {
            flex-direction: column-reverse;
            justify-content: center;
        }

        &__content {
            display: block;
        }

        &__art {
            display: flex;
            align-items: center;
            justify-content: center;
            flex: 1;
            height: 508px;
            margin-left: 24px;
            margin-top: 80px;
            background: var(--overlay-color) url(/contacts-overlay.jpg);
            background-size: cover;
            background-position: center;
            border-radius: 6px;

            @media screen and (max-width: 628px) {
                max-height: 130px;
                min-height: 130px;
                margin: 0;

                & > div {
                    max-height: 150px !important;
                    margin-top: -12px !important;
                }
            }
        }

        &__list {
            list-style: none;
            display: flex;
            flex-direction: column;
            margin: 0;
            padding: 0;
        }

        &__item {
            display: flex;
            flex-direction: column;
            margin-bottom: 16px;
        }

        &__link {
            margin-bottom: 6px;
            text-decoration: none;
            background-color: var(--overlay-color);
            padding: 12px 18px;
            border-radius: 6px;
        }

        &__label {
            margin: 0 0 6px 0;
            line-height: 1;
        }

        &__value {
            display: block;
            margin: 0;
            font-weight: lighter;
            color: var(--link-color);
        }

        &__icon {
            width: 18px;
            height: 18px;
            object-fit: contain;
            vertical-align: middle;
            color: var(--background-color);
        }
    }
</style>
