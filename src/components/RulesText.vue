<template>
    <p>
        Rules and validation:
    </p>
    <ol class="osg-ordered-list">
        <li class="osg-ordered-list__item">Form cannot be submitted empty.</li>
        <li class="osg-ordered-list__item">Characters must be valid Roman Numeral Characters.</li>
        <li class="osg-ordered-list__item">Characters must be in valid order.</li>
        <li class="osg-ordered-list__item">It is case in-sensitive.</li>
        <li class="osg-ordered-list__item">It does not support numbers greater than 3999 (MMMCMXCIX).</li>
    </ol>
    <p>
        Error will be shown if:
    </p>
    <ol class="osg-ordered-list">
        <li class="osg-ordered-list__item">Form is submitted empty.</li>
        <li class="osg-ordered-list__item">String contains invalid Roman Numeral Characters.</li>
        <li class="osg-ordered-list__item">Character is not in valid order.</li>
    </ol>
</template>

<script>
export default {
    name: 'RulesText',
}
</script>