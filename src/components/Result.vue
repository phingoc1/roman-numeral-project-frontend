<template>
    <div class="osg-status-message osg-status-message--success osg-margin-top-4">
        <p class="osg-status-message__heading"><span class="osg-status-message__icon osg-icon--success-square" aria-hidden="true"></span>{{result}}</p>
    </div>
</template>

<script>
export default {
    name: 'Result',
    props: {
        result: {
            type: String,
            default: ''
        }
    }
}
</script>