<template>
  <div>
    <h1>My name is {{ name }}</h1>
  </div>

  <div v-if="pending">Loading projects...</div>

  <div>
    <h2>Projects</h2>
    <ul>
      <li v-for="project in projects" :key="project.name">
        <h3>{{ project.name }}</h3>
        <p>{{ project.description }}</p>
      </li>
    </ul>
  </div>

  <div v-if="pending">Loading blogs...</div>

  <div>
    <h2>Blogs</h2>
    <ul>
      <li v-for="blog in blogs" :key="blog.title">
        <h3>{{ blog.title }}</h3>
        <h4>{{ blog.content }}</h4>
      </li>
    </ul>
  </div>
</template>

<script setup>
  const name = "Adithya Hewage";
  const {data: projects, pending, error, } = useFetch("http://localhost:5000/projects");
  const {data: blogs, pending1, error1,} = useFetch("http://localhost:5000/blogs");
</script>