<script setup lang="ts">

import{
    getCommentsById,
	type ArticleComment,
} from "../requests/article"
import {ref} from 'vue'





const thisArticlesComments = ref<ArticleComment[]>([]);
thisArticlesComments.value = getCommentsById(1);




</script>

<template>
<div v-for="(comment, index) in thisArticlesComments" class="comment">
	<h3>{{ comment.name }}</h3>
	<p>{{ comment.comment }} </p>
	<p> {{ comment.date }}<span><button :id="index">Delete</button></span></p>
	
</div>
</template>