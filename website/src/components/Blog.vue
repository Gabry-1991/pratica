<template>
  <div class="container--blog">
    <div class="container--title">
      <h3 class="title">Il Blog</h3>
    </div>

    <div
      v-for="(blog, idx) of blogs"
      :key="idx"
      class="container--blogs"
      :class="{ 'last-blog': idx === blogs.length - 1 }"
    >
      <div class="container--image">
        <img height="84" width="84" :src="blog.img" alt="author image" />
      </div>

      <div class="container--details">
        <div class="blog-title">{{ blog.title }}</div>
        <div class="blog-author">Di {{ blog.author }}</div>
      </div>
    </div>

    <div class="container--all-blogs">
      <div class="all-blogs">Tutti i blog</div>
      <i class="fa-solid fa-arrow-right" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blogs: [
        {
          title: "Il Becco dell'oca",
          author: "Paolo Dell'Oca",
          img: 'authors/author-9.jpeg',
        },
        {
          title: 'Disarmato',
          author: 'Pasquale Pugliese',
          img: 'authors/author-10.jpeg',
        },
        {
          title: 'Battitiperminuto',
          author: 'Lorenzo Maria Alvaro',
          img: 'authors/author-11.jpeg',
        },
        {
          title: 'La Zanzarella',
          author: 'Elena Zanella',
          img: 'authors/author-12.jpeg',
        },
        {
          title: 'Impact Q&A',
          author: 'Laura Orestano',
          img: 'authors/author-13.jpeg',
        },
      ],
    }
  },
}
</script>

<style scoped>
.container--blog {
  font-weight: 700;
  font-family: 'Anybody', serif;

  height: 212px;
  background: #fff;

  display: grid;
  grid-template-columns: repeat(6, 1fr);
}

.container--title {
  height: 100%;
  border-right: 1px solid #000;

  display: flex;
  align-items: center;
  justify-content: center;
}

.container--image {
  height: 84px;
  width: 84px;

  border-radius: 100%;
  overflow: hidden;
}

.container--blogs {
  height: 100%;
  border-right: 1px solid #000;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.75rem;

  &:last-of-type {
    border: none;
  }
}

.container--details {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
}

.container--all-blogs {
  display: none;
}

.title {
  color: var(--primary-red);
  font-size: 40px;
}

.blog-title {
  font-size: 18px;
}

.blog-author {
  font-size: 14px;
  font-weight: 400;
}

@media (max-width: 1030px) {
  .container--blog {
    height: calc(188px * 3);
    background: #000;
    border-top: 1px solid #000;
    border-bottom: 1px solid #000;

    grid-template-columns: repeat(2, 1fr);
    gap: 1px;
  }

  .container--title {
    background: #fff;
    border: none;
  }

  .container--blogs {
    background: #fff;
    border: none;
  }

  .container--all-blogs {
    background: #fff;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
  }

  .title {
    font-size: 24px;
  }

  .blog-title {
    font-size: 16px;
  }

  .last-blog {
    display: none;
  }
}
</style>
