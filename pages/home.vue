// https://velog.io/@1-blue/tailwindCss-markdown-%EC%A0%81%EC%9A%A9
<template>
    <div>test
    <nuxt-link v-for="t in test" :key="t.title" :to="t._path">{{ t.title }}</nuxt-link>
    </div>

</template>

<script setup lang="ts">
/*
const { data } = await useAsyncData(`content-1`, async () => {

  
    const test = await queryContent().find()
    console.log('test',test)
  return {
    test
  };
});
    console.log('data',data)
    const test = data.value.test
*/ const test = []
// const { page } = useContent();
// useSeoMeta({
//     description: page.value.description,
//     ogDescription: page.value.description,
//     ogImage: page.value.thumbnail ?? '/assets/banner.png',
// });
// useHead({
//     meta: [
//         { name: 'keywords', content: page.value.categories?.split(' ').join(', ') },
//         { name: 'robots', content: 'index, follow' },
//     ],
// });

const getDate = (value: string) => {
    try {
        const tmp = new Date(value);
        const year = tmp.getFullYear();
        const month = tmp.getMonth() + 1 >= 10 ? tmp.getMonth() + 1 : `0${tmp.getMonth() + 1}`;
        const date = tmp.getDate() >= 10 ? tmp.getDate() : `0${tmp.getDate()}`;
        return `${year}.${month}.${date}`;
    } catch (e) {
        return '';
    }
};

const convertImgPath = (data: any) => {
    return JSON.parse(JSON.stringify(data).replace(/\/assets/g, '/images'));
};

// const components = {};

// let contentDoc = ref();
// const { setIsShow, setX } = useCat();
// onMounted(() => {
//     window.addEventListener('scroll', () => {
//         // console.log(
//         //     "------------content",
//         //     contentDoc.value.getBoundingClientRect()
//         // );

//         if ((contentDoc.value as HTMLElement)?.getBoundingClientRect().y - 64 <= scrollY) {
//             setIsShow(true);
//         } else {
//             setIsShow(false);
//         }

//         // console.log((contentDoc.value as HTMLElement)?.offsetTop);
//         // console.log((contentDoc.value as HTMLElement)?.scrollTop);
//         // console.log((contentDoc.value as HTMLElement)?.clientTop);
//         // console.log(window.scrollY);

//         // console.log((contentDoc.value as HTMLElement)?.offsetHeight);
//         // console.log((contentDoc.value as HTMLElement)?.scrollHeight);
//         // console.log((contentDoc.value as HTMLElement)?.clientHeight);

//         const progress = ((window.scrollY - (contentDoc.value as HTMLElement)?.offsetTop) / ((contentDoc.value as HTMLElement)?.scrollHeight - 512 - 288)) * 100;

//         if (progress) {
//             setX(progress);
//         }

//         // console.log(progress);
//     });
// });
</script>

<style>
h2 {
    font-weight: bold !important;
    font-size: 28px !important;
}
a {
    text-decoration: none !important;
}

pre {
    background-color: transparent !important;
    border: 1px solid #1f2937 !important;
    color: #1f2937 !important;
}

p > code {
    border: 1px solid #1f2937 !important;
    background-color: #1f2937 !important;
    color: white !important;
    border-radius: 4px;
}

p > code::before {
    display: none;
}
p > code::after {
    display: none;
}
</style>
