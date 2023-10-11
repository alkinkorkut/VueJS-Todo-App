<template>
    <small class="d-flex justify-content-end green"> {{ itemCount }} todos are available. </small>
</template>

<script>
export default {
    props: ["itemCount"]
};
</script>