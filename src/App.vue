<template>
    <div>
       <Header />

        <div class="content">
            <Content />
        </div>

        <Footer /> 
    </div>

</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Content from './components/Content.vue'

export default {
    name: 'App',
    components: {
        Header: Header,
        Footer: Footer,
        Content: Content
    }
}
</script>

<style lang="scss">
@import url('https://ukeweb-styleguide-cdn.s3.eu-central-1.amazonaws.com/0.99.105/osg.css')
</style>
