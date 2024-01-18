<template>
  <div class="course-wrapper" :style="{ marginBottom: spacing }">
    <div class="highlight"></div>
    <div>
      <p>{{ courseTitle }}</p>
    </div>
    <div class="action-buttons">
      <router-link :to="`/instructor/editlesson`" class="edit-button">
        <Icon name="tabler:edit" class="font-bold text-2xl" />
      </router-link>
      <router-link :to="`/instructor/viewmaterial`" class="view-button">
        <Icon name="ph:files" class="font-bold text-2xl" />
      </router-link>
      <button @click="deleteCourse" class="delete-button">
        <Icon name="material-symbols:delete-outline" class="font-bold text-2xl" />
      </button>
     
    </div>
  </div>
</template>

<script>
export default {
  props: {
    lessonId: {
      type: Number,
      required: true,
    },
    courseTitle: {
      type: String,
      default: "Lesson",
    },
    spacing: {
      type: String,
      default: "1rem",
    },
  },
  methods: {
    deleteCourse() {
      console.log(`Deleting lesson with ID ${this.lessonId}`);
    },
  },
};
</script>

<style scoped>
.course-wrapper {
  position: relative;
  width: 100%;
  padding: 1rem;
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  border-radius: 6px;
  overflow: hidden;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.highlight {
  position: absolute;
  top: 0;
  left: 0;
  width: 0.7rem;
  height: 100%;
  background: #2b348f;
}

.action-buttons {
  display: flex;
}

.edit-button,
.delete-button,
.view-button {
  margin-left: 10px;
  padding: 6px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none; 
  color: #fff; 
}

.edit-button {
  background-color: #2b348f;
}

.view-button {
  background-color: #4caf50;
}

.delete-button {
  background-color: #ff7e3e;
}
</style>
