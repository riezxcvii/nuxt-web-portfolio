<template>
  <div>
    <!-- animated background template -->
    <div>
      <ul class="background z-10 h-full">
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </div>

    <div class="min-h-screen">
      <div class="sticky top-0">
        <NavBar />
      </div>

      <div class="justify-center items-center">
        <Contact id="id.home" />
      </div>
    </div>
  </div>
</template>

<script>
const id = [
  { home: '#home', skills: '#skills', projects: '#projects' }
]
</script>
