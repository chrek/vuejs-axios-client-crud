<template>
  <div class="submit-form">
    <div v-if="!submitted">
      <div class="form-group">
        <label for="title">Title</label>
        <input
          type="text"
          class="form-control"
          id="title"
          required
          v-model="article.title"
          name="title"
        />
      </div>

      <div class="form-group">
        <label for="description">Description</label>
        <input
          class="form-control"
          id="description"
          required
          v-model="article.description"
          name="description"
        />
      </div>

      <button @click="saveArticle" class="btn btn-success">Submit</button>
    </div>

    <div v-else>
      <h4>You submitted successfully!</h4>
      <button class="btn btn-success" @click="newArticle">Add</button>
    </div>
  </div>
</template>

<script>
import ArticleDataService from "../services/ArticleDataService";

export default {
  name: "add-article",
  data() {
    return {
      article: {
        id: null,
        title: "",
        description: "",
        published: false
      },
      submitted: false
    };
  },
  methods: {
    saveArticle() {
      var data = {
        title: this.article.title,
        description: this.article.description
      };

      ArticleDataService.create(data)
        .then(response => {
          this.article.id = response.data.id;
          console.log(response.data);
        })
        .catch(e => {
          console.log(e);
        });

      this.submitted = true;
    },
    newArticle() {
      this.submitted = false;
      this.article = {};
    }
  }
};
</script>

<style>
div.container {
  background: cadetblue;
}

div.form-group > input {
  border: 1px solid #a4a4a4;
  padding: 15px 20px;
  border-radius: 4px;
  width: 100%; /* set width relatively to the parent container with fixed width */
  margin-bottom: 10px;
  background: #f8f8ff;
}

.submit-form {
  max-width: 300px;
  margin: auto;
}
</style>
