<template>
    <div class="holder">
        <div class="logger">
            <div
                v-for="( i, key ) in logs"
                :key ="key"
                :class="'log ' + i.class_name"
            >
                <span v-html="i.log"></span>
            </div>
        </div>
    </div>
</template>

<script>

import { getDailyLogRecordsPointer } from '../../data/records_ipc';

export default {
    name : 'Logger',
    data : () => ({
        logs : getDailyLogRecordsPointer(),
    }),
}
</script>

<style scoped>
    .green{
        color: green;
    }
    .red{
        color: red;
    }
    .grey{
        color: grey;
    }
    .orange{
        color: orange;
    }
    .log{
        min-height: 15px;
        font-size: 14px;
        padding: 0;
        margin-top: 0;
        margin-bottom: 0;
    }
    .holder{
        padding: 0;
        margin: 0;
        border: 0;
        height: 100%;
        background-color: rgb(30,30,30);
        font-family: "Roboto", "Helvetica", "Arial", sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        color: rgba(0, 0, 0, 0.87);
        background-color: #fafafa;
    }
    .logger{
        height: calc(100% - 15px);
        width: 100%;
        background-color:transparent;
        position: relative;
        overflow-y: scroll;
    }
</style>