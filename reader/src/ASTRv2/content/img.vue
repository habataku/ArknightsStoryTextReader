<template>
    <n-image
        :class="{images: imgtype=='images' || bgMode=='full', backgrounds:imgtype=='backgrounds'&&bgMode=='stripe'}"
        :src="`https://raw.githubusercontent.com/Aceship/Arknight-Images/main/avg/${imgtype}/${line.attributes.image}.png`" />
</template>

<script>
import func from '../func'
export default {
    data() {
        return {
            line: this.inputline,
            imgtype: this.background ? 'backgrounds' : 'images',
            bgMode: func.bgMode
        }
    },
    props: {
        inputline: Object,
        background: {
            type: Boolean,
            default: false
        }
    }
}
</script>

<style>
.line .images img {
    max-width: 500px;
    max-height: 300px;
    /*horizontal center*/
    margin-left: calc(100vh/7*2);
}

.line .backgrounds img {
    margin: 10px;
    /*horizontal center*/
    margin-left: calc(100vh/7*2);
    height: 150px;
    width: 700px;
    object-fit: none !important;
}

@media(max-width: 750px) {
    .line .images img {
        margin-left: 5%;
        max-width: 90vw;
    }

    .line .backgrounds img {
        margin: 10px;
        max-width: 90vw;
        /*horizontal center*/
        margin-left: 5%;
        object-fit: scale-down !important;
    }
}
</style>