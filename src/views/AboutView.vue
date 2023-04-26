<template>
    <div class="about">
        <span v-for="u in users">{{u.id}}-{{u.name}}&nbsp;&nbsp;</span>
    </div>
    <el-row>
        <el-col :span="24" style="background-color: aqua">324<div class="grid-content ep-bg-purple-dark" /></el-col>
    </el-row>
</template>

<script>
export default {
    data() {
        return {
            users: [],
        }
    }, methods: {
        init() {
            this.axios.get("http://localhost:9090/list").then(res => {
                this.users = res.data
            })
        }
    }, created() {
        this.init()
    }
}
</script>

<style>
@media (min-width: 1024px) {
    .about {
        min-height: 100vh;
        display: flex;
        align-items: center;
    }
}
</style>
