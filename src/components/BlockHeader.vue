<template>
    <div class="top-block">
        <div class="block-name">{{ name }}</div>
        <div class="container">
            <div class="block-desc">{{ description }}</div>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'BlockHeader',
    props: ['name', 'description']
  }
</script>

<style scoped>
    .top-block {
        position: relative;
        height: 220px;
    }

    .top-block::before {
        content: '-';
        color: transparent;
        display: inline-block;
        width: 300px;
        height: 7px;
        background: var(--danger);
    }

    .block-name {
        font-family: 'Fira Sans', sans-serif;
        z-index: 0;
        padding: 30px 0;
        font-weight: 700;
        font-size: 120px;
        line-height: 120px;
        opacity: 0.1;
        margin-left: 30px;
        color: #fff;
        text-transform: uppercase;
    }

    .block-desc {
        font-family: 'Fira Sans', sans-serif;
        z-index: 1;
        font-size: 32px;
        line-height: 30px;
        font-weight: 300;
        position: absolute;
        top: 95px;
        margin-left: 100px;
        opacity: 0.8;
        color: var(--danger);
    }

    @media screen and (max-width: 768px) {
        .top-block {
            height: auto;
            padding-bottom: 50px;
        }

        .top-block::before {
            width: 100%;
        }

        .block-name {
            font-size: 48px;
            line-height: 48px;
            padding: 10px;
            margin-left: 0;
            text-align: center;
        }

        .block-desc {
            position: relative;
            top: 0;
            margin-left: 0;
            font-size: 24px;
        }
    }
</style>