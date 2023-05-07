<template>
    <div class="osg-status-message osg-status-message--danger osg-margin-top-4">
        <p class="osg-status-message__heading"><span class="osg-status-message__icon osg-icon--error-hexa" aria-hidden="true"></span>{{error}}</p>
    </div>
</template>

<script>
export default {
    name: 'Error',
    props: {
        error: {
            type: String,
            default: ''
        }
    }
}
</script>