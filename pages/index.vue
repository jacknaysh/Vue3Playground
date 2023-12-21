<script setup lang="ts">
import {
	getCommentsById,
	addNewComment,
	type ArticleComment, //importing a type
} from "../requests/article";

const name = ref("");
const commentInput = ref("");
//what is <> for?
const thisArticlesComments = ref<ArticleComment[]>([]);

async function submitComment() {}

/**
 * Imagine this is a news article that has been selected from a site like
 *
 *  https://www.bbc.co.uk/news
 *
 * 1. get the comments for this article via the dummy api call and render them in place of the placeholder comment
 *
 * 2. lets plug in the form to the api call to add a new comment
 *
 * 3. render the new comment in the list of comments
 *
 * 4. break the comments into a seperate component
 *
 *  https://www.bbc.co.uk/news - lets do a component and data 'breakdown' of this page, if we were going to build it in vue
 *
 * 5. we have magically been granted admin privilages, lets add a delete button to each comment
 */
</script>

<template>
	<main class="news-article">
		<article class="news-article-header">
			<div class="news-article-title">
				<img
					src="https://picsum.photos/2500"
					alt="random image"
					width="100%"
					height="300px"
				/>
				<h1>Important News Article</h1>
			</div>
			<div class="news-article-date">
				John Smith
				{{
					new Date(
						new Date().getTime() - 175_000_000
					).toLocaleString()
				}}
			</div>
			<h2>Lorem</h2>
			<p>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Hic
				saepe, sint eum corrupti asperiores amet dolorem facilis atque,
				quam quis iusto dolorum ea odio cumque, aliquid veritatis quas
				consequuntur pariatur. Lorem ipsum, dolor sit amet consectetur
				adipisicing elit. Hic saepe, sint eum corrupti asperiores amet
				dolorem facilis atque, quam quis iusto dolorum ea odio cumque,
				aliquid veritatis quas consequuntur pariatur. Lorem ipsum, dolor
				sit amet consectetur adipisicing elit. Hic saepe, sint eum
				corrupti asperiores amet dolorem facilis atque, quam quis iusto
				dolorum ea odio cumque, aliquid veritatis quas consequuntur
				pariatur. Lorem ipsum, dolor sit amet consectetur adipisicing
				elit. Hic saepe, sint eum corrupti asperiores amet dolorem
				facilis atque, quam quis iusto dolorum ea odio cumque, aliquid
				veritatis quas consequuntur pariatur. Lorem ipsum, dolor sit
				amet consectetur adipisicing elit. Hic saepe, sint eum corrupti
				asperiores amet dolorem facilis atque, quam quis iusto dolorum
				ea odio cumque, aliquid veritatis quas consequuntur pariatur.
			</p>
			<h2>Ipsum</h2>
			<p>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Hic
				saepe, sint eum corrupti asperiores amet dolorem facilis atque,
				quam quis iusto dolorum ea odio cumque, aliquid veritatis quas
				consequuntur pariatur. Lorem ipsum, dolor sit amet consectetur
				adipisicing elit. Hic saepe, sint eum corrupti asperiores amet
				dolorem facilis atque, quam quis iusto dolorum ea odio cumque,
				aliquid veritatis quas consequuntur pariatur. Lorem ipsum, dolor
				sit amet consectetur adipisicing elit. Hic saepe, sint eum
				corrupti asperiores amet dolorem facilis atque, quam quis iusto
				dolorum ea odio cumque, aliquid veritatis quas consequuntur
				pariatur.
			</p>
			<h2>Dolor</h2>
			<p>
				Lorem ipsum, dolor sit amet consectetur adipisicing elit. Hic
				saepe, sint eum corrupti asperiores amet dolorem facilis atque,
				quam quis iusto dolorum ea odio cumque, aliquid veritatis quas
				consequuntur pariatur.
			</p>
		</article>
		<form @submit.prevent="submitComment" class="comment-input-form">
			<hr />

			<h2>leave a comment:</h2>
			<label for="name">Name</label>
			<input type="text" name="name" v-model="name" />
			<br />
			<label for="comment">Comment</label>
			<textarea type="text" name="comment" v-model="commentInput" />
			<br />
			<button type="submit">Submit</button>
			<hr />
		</form>
		<div class="comments-section">
			<h2>Comments:</h2>
			<div class="comment">
				<div class="comment-header">
					<h3>Name: name | date</h3>
				</div>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit.
					Quisquam, voluptatum. Quisquam voluptatibus, quia, quos,
					voluptate quod quas quibusdam quidem voluptatum dolorum
					voluptas quae. Quisquam, voluptatum. Quisquam voluptatibus,
					quia, quos, voluptate quod quas quibusdam quidem voluptatum
					dolorum voluptas quae.
				</p>
				<hr />
			</div>
		</div>
	</main>
</template>

<style scoped>
.news-article {
	font-family: "Comic Sans MS";
	background-color: #f5f5f5;
	padding: 20px;
	border-radius: 5px;
}

.news-article-header {
	margin-bottom: 20px;
}

.news-article-title {
	margin-bottom: 10px;
}

.news-article-title img {
	margin-right: 10px;
}

.news-article-date {
	font-size: 14px;
	color: #888;
	margin-bottom: 10px;
}

.comment-input-form {
	margin-top: 20px;
}

.comment-input-form label {
	display: block;
	margin-bottom: 5px;
}

.comment-input-form input,
.comment-input-form textarea {
	width: 100%;
	padding: 10px;
	border: 1px solid #ccc;
	border-radius: 5px;
	margin-bottom: 10px;
}

.comment-input-form button {
	padding: 10px 20px;
	background-color: #007bff;
	color: #fff;
	border: none;
	border-radius: 5px;
	cursor: pointer;
}

.comments-section {
	margin-top: 20px;
}

.comment {
	margin-bottom: 20px;
}

.comment-header {
	font-size: 16px;
	font-weight: bold;
	margin-bottom: 10px;
}

.comment p {
	margin-bottom: 10px;
}
</style>
