<template>
<div>
    <el-menu
        :default-active="activeIndex2"
        class="el-menu-demo"
        mode="horizontal"
        @select="handleSelect"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b">

        <!-- <el-menu-item index="1">Front Page</el-menu-item>
        <el-menu-item index="2">Finance</el-menu-item>
        <el-menu-item index="3">{{MenuItems[0].name}}</el-menu-item> -->

        <el-menu-item v-for="item in MenuItems" :index="item.id" :key="item.id">
            {{item.name}}
        </el-menu-item>

    </el-menu>
</div>

</template>

<script>


export default {
    name: 'navbar',

    props: ["MenuItems"],

    data() {
        return {
            activeIndex: '1',
            activeIndex2: '1'
        };
    },
    methods: {
        handleSelect(key, keyPath) {
            console.log(key, keyPath);
        }
    }

    

}
</script>