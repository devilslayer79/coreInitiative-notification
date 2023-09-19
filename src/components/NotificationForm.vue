<template>
    <div>
      <h2>Form Input Notification</h2>
      <form @submit.prevent="addNotification">
        <div>
            <label for="name" class="custom-label">Name:</label>
            <input type="text" id="name" v-model="newNotification.name" class="custom-input" required>
        </div>
        <div>
            <label for="action" class="custom-label">Action:</label>
            <input type="text" id="action" v-model="newNotification.action" class="custom-input" required>
        </div>
        <div>
            <label for="message" class="custom-label">Message:</label>
            <input type="text" id="message" v-model="newNotification.message" class="custom-input" required>
        </div>
        <div>
            <label for="time" class="custom-label">Time:</label>
            <input type="text" id="time" v-model="newNotification.time" class="custom-input" required>
        </div>
        <br>
        <div>
          <button type="submit" class="custom-button">Add Notification</button>
        </div>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newNotification: {
          name: "",
          action: "",
          message: "",
          time: ""
        }
      };
    },
    methods: {
      addNotification() {
        // tambah notifikasi ke array notifs
        this.$emit("add-notification", this.newNotification);
        // reset form
        this.newNotification = {
          name: "",
          action: "",
          message: "",
          time: ""
        };
      }
    }
  };
  </script>

<style scoped>
.custom-button {
  background-color: #3498db; /* Warna latar belakang */
  color: #fff; /* Warna teks */
  border: none;
  padding: 6px 8px; 
  border-radius: 5px; /* Membuat sudut tombol menjadi melengkung */
  cursor: pointer;
  transition: background-color 0.3s ease; /* Animasi perubahan warna latar belakang */
}

.custom-button:hover {
  background-color: #2980b9; /* Warna latar belakang saat dihover */
}

.custom-label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px; /* Jarak antara label dengan input */
}

.custom-input {
  padding: 10px; 
  border: 1px solid #ccc; 
  border-radius: 5px; /* Membuat sudut input menjadi melengkung */
  width: 100%; /* Lebar input mengisi seluruh kontainer */
}

</style>
  