<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.panel-body {
    font-family: Arizonia, sans-serif;
    color: #6e6e6e;
    font-size: 24px;
}

.quote {
    cursor: pointer;
}

.quote:hover {
    background-color: #ffe2e2;
}
</style>
