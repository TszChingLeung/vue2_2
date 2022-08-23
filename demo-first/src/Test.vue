<template>
    <div class="test-box">
        <h3>这是用户自定义的 Test.vue --- {{ username }}</h3>
        <button @click="changeName">修改用户名</button>
    </div>
</template>

<script>
// 默认导出，这是固定写法！（每一个 .vue 组件中要定义 script 都必须写这行代码 export default{} ）
export default{
    // 数据源
    // 注意： .vue 组件中的 data 不能像之前一样，不能指向对象。
    // 注意：组件中的 data 必须是一个函数
    // data: { // 这个写法是错误的
    //     username: 'zs'
    // }
    data() {
        // 这个 return 出去的 {} 中，可以定义数据
        return {
            username: 'admin'
        }
    },
    methods: {
        changeName() {
            // 在组件中， this 就表示当前组件的示例对象
            console.log(this);
            this.username = '娃哈哈';
        }
    },
    // 当前组件中的侦听器
    watch: {},
    // 当前组件中的计算属性
    computed: {},
    filters: {}
}
</script>

<style lang="less">
    .test-box {
        background-color: pink;
        /* less 语法 */
        h3 {
            color: red;
        }
    }
</style>