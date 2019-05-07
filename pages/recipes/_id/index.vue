<template>
  <section class="single-recipe">
    <h1>{{recipe.title}}</h1>
    <div>
      <img
        class="recipe-image"
        :src="recipe.thumbnail"
        :alt="recipe.title"
      />
      <p>{{recipe.description}}</p>
    </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious Pizza",
              previewText: "Awesome Pizza!",
              description: "This is a really a delicious meal!",
              thumbnail: "https://foodrevolution.org/wp-content/uploads/2018/04/blog-featured-diabetes-20180406-1330.jpg",
            },
            {
              id: "2",
              title: "Delicious Sea Food",
              previewText: "Awesome Sea Food!",
              description: "This is a really a delicious meal!",
              thumbnail: "https://upload.wikimedia.org/wikipedia/commons/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg",
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipe-image {
  max-width: 100%;
  max-height: 600px;
}
</style>
