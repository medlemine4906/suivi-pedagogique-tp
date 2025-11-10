<template>
  <div class="container mt-5">
    <h2 class="mb-4">Liste des étudiants</h2>

    <table class="table table-bordered">
      <thead class="table-light">
        <tr>
          <th>Matricule</th>
          <th>Nom</th>
          <th>Prénom</th>
          <th>Filière</th>
          <th>Niveau</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="etudiant in etudiants" :key="etudiant.id">
          <td>{{ etudiant.matricule }}</td>
          <td>{{ etudiant.nom }}</td>
          <td>{{ etudiant.prenom }}</td>
          <td>{{ etudiant.filiere }}</td>
          <td>{{ etudiant.niveau }}</td>
        </tr>
        <tr v-if="etudiants.length === 0">
          <td colspan="5" class="text-center text-muted">Aucun étudiant trouvé</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
defineProps({
  etudiants: {
    type: Array,
    required: true
  }
});
</script>

<style scoped>
.container {
  max-width: 900px;
}
</style>