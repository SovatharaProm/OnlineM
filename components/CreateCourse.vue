<template>
  <div class="course-wrapper" :style="{ marginBottom: spacing }">
    <div class="highlight"></div>
    <div>
      <p>{{ courseTitle }}</p>
      <p style="color: #8A8A8A;">Lesson: 17h</p>
    </div>
    
    <NuxtRating :read-only="true" :ratingValue="4" />

    <div class="action-buttons">
      <router-link :to="`/instructor/editcourse`" class="edit-button">
        <Icon name="tabler:edit" class="font-bold text-2xl" />
      </router-link>
      <router-link :to="`/instructor/viewmaterial`" class="view-button">
        <Icon name="icon-park-outline:find" class="font-bold text-2xl" />
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
    courseTitle: {
      type: String,
      default: 'Cloud Computing' 
    },
    spacing: {
      type: String,
      default: '1rem' 
    }
  },
  methods: {
    editCourse() {
     
      console.log('Edit course clicked');
    },
    deleteCourse() {
      
      const index = this.$parent.courses.findIndex(course => course.title === this.courseTitle);
      if (index !== -1) {
        // Remove the course from the courses array
        this.$parent.courses.splice(index, 1);
        console.log(`Course "${this.courseTitle}" deleted`);
      }
    }
  }
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
.view-button,
.delete-button {
  margin-left: 10px;
  padding: 6px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  display: flex; 
  align-items: center; 
}

.edit-button {
  background-color: #2B348F;
  color: #fff;
}

.delete-button {
  background-color: #FF7E3E;
  color: #fff;
}

.view-button {
  background-color: #4caf50;
  color: #fff;
}
</style>