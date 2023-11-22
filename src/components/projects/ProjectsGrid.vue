<template>
  <section class="projects-grid container" id="projects">
    <h3>Projects</h3>
    <!--  <ProjectCard
      v-for="project in highlightedProjects"
      :key="project.title"
      :thumbnail="project.thumbnail"
      :title="project.title"
      :description="project?.description"
      :tags="project.tags"
      :github="project.github"
    /> -->
    <div class="project-card">
      <figure class="project-thumbnail">
        <img src="/src/assets/img/miraelmenu.PNG" alt="me" loading="lazy" class="project-card__image" width="500"
          height="200" />

      </figure>
      <div class="project-card__content">
        <div class="project-card__header">
          <h4>Miraelmenu</h4>
          <p>Pagina web que ofrece el servicio de crear menus personalizados y accesibles mediante un codigo QR. Hecho en wordpress</p>
        </div>
        <div class="project-card__footer">

        <AppLink variant="button" full isExternal :to="'https://miraelmenu.com/'" :aria-labelledby="``">
          Link
        </AppLink>
        </div>
      </div>
    </div>
    <div class="project-card">
      <figure class="project-thumbnail">
        <img src="/src/assets/img/todolist.PNG" alt="me" loading="lazy" class="project-card__image" width="500"
          height="200" />

      </figure>
      <div class="project-card__content">
        <div class="project-card__header">
          <h4 >TodoList</h4>
          <p>Un proyecto personal en el que aplique mis primeros conocimientos en React</p>
        </div>
        <div class="project-card__footer">
          <AppLink variant="button" full isExternal :to="'https://apptodolistnottaken.netlify.app/'" :aria-labelledby="``">
          Link
        </AppLink>
        </div>
      </div>
    </div>
    <div class="project-card">
      <figure class="project-thumbnail">
        <img src="/src/assets/img/vatomlm.PNG" alt="me" loading="lazy" class="project-card__image" width="500"
          height="200" />

      </figure>
      <div class="project-card__content">
        <div class="project-card__header">
          <h4>Vatomlm</h4>
          <p>Proyecto sobre una pagina web de gestion de inversiones.</p>
        </div>
        <div class="project-card__footer">
          <AppLink variant="button" full isExternal :to="'https://vatomlm.com/'" :aria-labelledby="``">
          Link
        </AppLink>
        </div>
      </div>
    </div>
    
  </section>
</template>

<script setup>
import projects from '@content/projects/projects.json'

const highlightedProjects = Object.values(projects).filter(
  (project) => project.pinned
)
</script>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(400px, 100%), 1fr));
  grid-gap: 1rem;
  margin-block-end: 4rem;

  h3 {
    grid-column: 1 / -1;
    text-transform: uppercase;
    margin-block-start: 2rem;
  }
}

.project-card {
  display: flex;
}

.project-thumbnail {
  flex-basis: 50%;
  border-radius: var(--radius-default) 0 0 var(--radius-default);
}

.project-card__image {
  border-radius: inherit;
  object-fit: cover;
  object-position: top center;
  height: 200px;
  min-height: 100%;

  &.lozad {
    filter: blur(0);
  }
}

.project-card__content {
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  flex-basis: 50%;
  background-color: var(--bg-color-lighter, var(--color-gray-800));
  padding: 1.125rem;
  border-radius: 0 var(--radius-default) var(--radius-default) 0;
  border: 1px solid transparent;
}

.project-card__header {
  & h4 {
    font-size: var(--text-lg);
  }

  & p {
    margin-block-end: 10px;
    opacity: 0.7;
  }
}

.project-card__footer {
  .tags {
    margin-block-end: 1rem;
  }
}

body[data-theme='light'] {
  .project-card__content {
    border: var(--border);
  }
}

@media (--vw-sm) {
  .project-card {
    flex-direction: column;
  }
}
</style>
