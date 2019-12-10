<script>
export let host;
export let imgName;
export let alt;
export let c = "";
export let style = "";

</script>

<style>





</style>

<picture>
    <source type="image/webp"
        srcset="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=="
        data-srcset="https://res.cloudinary.com/{host}/image/upload/w_200,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 200w,
                https://res.cloudinary.com/{host}/image/upload/w_400,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 400w,
                https://res.cloudinary.com/{host}/image/upload/w_800,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 800w,
                https://res.cloudinary.com/{host}/image/upload/w_1200,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 1200w,
            https://res.cloudinary.com/{host}/image/upload/w_1600,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 1600w,
            https://res.cloudinary.com/{host}/image/upload/w_2400,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName} 2400w
            "
        sizes="800px">
    <source type="image/jpg"
        srcset="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=="
        data-srcset="https://res.cloudinary.com/{host}/image/upload/w_200,c_fit/q_auto/v1575995947/landing-page/{imgName} 200w,
                https://res.cloudinary.com/{host}/image/upload/w_400,c_fit/q_auto/v1575995947/landing-page/{imgName} 400w,
                https://res.cloudinary.com/{host}/image/upload/w_800,c_fit/q_auto/v1575995947/landing-page/{imgName} 800w,
                https://res.cloudinary.com/{host}/image/upload/w_1200,c_fit/q_auto/v1575995947/landing-page/{imgName} 1200w,
            https://res.cloudinary.com/{host}/image/upload/w_1600,c_fit/q_auto/v1575995947/landing-page/{imgName} 1600w,
            https://res.cloudinary.com/{host}/image/upload/w_2400,c_fit/q_auto/v1575995947/landing-page/{imgName} 2400w
            "
        sizes="800px">
        <img    src="https://res.cloudinary.com/{host}/image/upload/w_400,c_fit/f_webp/q_auto/v1575995947/landing-page/{imgName}"
                {alt}
                {style}
                data-sizes="auto"
                class="lazyload w-full {c}"
                sizes="800px"
                >
</picture>
