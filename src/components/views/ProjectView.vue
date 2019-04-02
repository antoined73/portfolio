<template>
<div>
    <section class="hero is-medium is-primary is-bold">
        <div class="hero-body">
        <p class="title" v-if="project">
            {{project.title}}
        </p>
        <p class="subtitle" v-if="project">
            {{project.description}}
        </p>
        </div>
    </section>
</div>
</template>

<script>
export default {
  name: 'ProjectView',
  components: {
  },
  data(){
      return {
          project : null
      }
  },
  created(){
      const projectId = parseInt(this.$route.params.projectId);
      this.project = this.$store.getters['projects/getProjectById'](projectId);
  }
}
</script>
