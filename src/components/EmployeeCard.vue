<template>
  <div class="card">
    <h1>Name: {{ name }}</h1>
    <h2>Age: {{ age }}</h2>
    <p>Salary: {{ salary }}</p>
    <p>Gender: {{ gender }}</p>
    <p>Married: {{ married ? "Yes" : "No" }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
    },
    age: {
      type: Number,
    },
    salary: {
      type: Number,
    },
    gender: {
      type: String,
    },
    married: {
      type: Boolean,
    },
  },
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  background: #ffffff;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  max-width: 320px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

h1 {
  color: #333;
  font-size: 22px;
  font-weight: 600;
  margin-bottom: 8px;
}

h2 {
  color: #555;
  font-size: 18px;
  margin-bottom: 16px;
}

p {
  color: #666;
  font-size: 16px;
  margin-bottom: 8px;
  font-weight: 500;
}

p:last-child {
  margin-bottom: 0;
}

p span {
  font-weight: 700;
  color: #2c3e50;
}

.card h1,
.card h2,
.card p {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>
