<script setup>
import { Link } from '@inertiajs/inertia-vue3';
import { ref } from 'vue';

const newTitle = ref('')
const newContent = ref('')
</script>

<template>
    Inertiatest<br>
    <Link href="/">リンク経由</Link><br>
    aaa
    <Link :href="route('inertia.index')">namae</Link><br>
    <Link :href="route('inertia.show', {id: 50})">route test</Link>


    <div class="mb-8">
        <input type="text" name="newTitle" v-model="newTitle">{{ newTitle }}<br>
        <input type="text" name="newContent" v-model="newContent">{{ newContent }}
        <br>
        <Link as="button" method="post" :href="route('inertia.store')"
              :data="{
                title: newTitle,
                content: newContent}">
              保存テスト
        </Link>
    </div>

</template>
