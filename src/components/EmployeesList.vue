<template>
  <div class="form-container">
    <div class="search-string">
      <label for="searchString">Search:</label>
      <input
        v-model="searchString"
        type="text"
        id="searchString"
        placeholder="Enter search name"
      />
    </div>

    <div class="search-string">
      <label for="gender">Gender:</label>
      <select v-model="gender" id="gender" name="gender">
        <option value="MALE">MALE</option>
        <option value="FEMALE">FEMALE</option>
      </select>
    </div>

    <div class="search-string">
      <label for="isChecked">
        <input
          class="checkbox"
          type="checkbox"
          v-model="isChecked"
          id="isChecked"
        />
        Married
      </label>
    </div>
  </div>
  <div class="wrapper">
    <EmployeeCard
      v-for="employee in filteredEmployees"
      :key="employee.id"
      :name="employee.name"
      :age="employee.age"
      :salary="employee.salary"
      :gender="employee.gender"
      :married="employee.married"
    />
  </div>
</template>

<script lang="ts">
import EmployeeCard from "./EmployeeCard.vue";
import { Employee } from "../types";

export default {
  components: {
    EmployeeCard,
  },
  computed: {
    filteredEmployees() {
      return this.allEmployees.filter((employee) => {
        return (
          employee.name
            .toUpperCase()
            .includes(this.searchString.toUpperCase()) &&
          employee.gender === this.gender &&
          employee.married === this.isChecked
        );
      });
    },
  },
  data() {
    return {
      isChecked: false,
      searchString: "",
      gender: "MALE" as "MALE" | "FEMALE",
      allEmployees: [
        {
          id: "1",
          name: "Jozef",
          surname: "Novak",
          age: 34,
          mobile: 123456789,
          email: "jozef.novak@example.com",
          adress: "Hlavná 12, Bratislava",
          salary: 2500,
          married: true,
          gender: "MALE",
        },
        {
          id: "2",
          name: "Mária",
          surname: "Kováčová",
          age: 28,
          mobile: "0987654321",
          email: "maria.kovacova@example.com",
          adress: "Kvetná 45, Košice",
          salary: 2200,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "3",
          name: "Peter",
          surname: "Horváth",
          age: 40,
          mobile: 987654321,
          email: "peter.horvath@example.com",
          adress: "Špitálska 9, Trnava",
          salary: 3000,
          married: true,
          gender: "MALE",
        },
        {
          id: "4",
          name: "Anna",
          surname: "Lukáčová",
          age: 32,
          mobile: 456789123,
          email: "anna.lukacova@example.com",
          adress: "Zelená 67, Nitra",
          salary: 2700,
          married: true,
          gender: "FEMALE",
        },
        {
          id: "5",
          name: "Marek",
          surname: "Tóth",
          age: 25,
          mobile: 567890123,
          email: "marek.toth@example.com",
          adress: "Májová 23, Žilina",
          salary: 1800,
          married: false,
          gender: "MALE",
        },
        {
          id: "6",
          name: "Veronika",
          surname: "Juhásová",
          age: 29,
          mobile: "0123456789",
          email: "veronika.juhasova@example.com",
          adress: "Špitálska 22, Nitra",
          salary: 2400,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "7",
          name: "Jakub",
          surname: "Mihál",
          age: 35,
          mobile: "9876543210",
          email: "jakub.mihal@example.com",
          adress: "Májová 54, Košice",
          salary: 2600,
          married: true,
          gender: "MALE",
        },
        {
          id: "8",
          name: "Eliška",
          surname: "Kováčová",
          age: 31,
          mobile: "567890987",
          email: "eliska.kovacova@example.com",
          adress: "Miestna 19, Bratislava",
          salary: 2200,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "9",
          name: "Tomáš",
          surname: "Farkaš",
          age: 38,
          mobile: "123987654",
          email: "tomas.farkas@example.com",
          adress: "Hlavná 45, Trnava",
          salary: 2900,
          married: true,
          gender: "MALE",
        },
        {
          id: "10",
          name: "Zuzana",
          surname: "Macková",
          age: 27,
          mobile: "345678901",
          email: "zuzana.mackova@example.com",
          adress: "Zelená 4, Košice",
          salary: 2000,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "11",
          name: "Martin",
          surname: "Dvorák",
          age: 33,
          mobile: "678901234",
          email: "martin.dvorak@example.com",
          adress: "Kvetná 11, Nitra",
          salary: 2750,
          married: true,
          gender: "MALE",
        },
        {
          id: "12",
          name: "Lýdia",
          surname: "Križová",
          age: 30,
          mobile: "987654321",
          email: "lydia.krizova@example.com",
          adress: "Hlavná 50, Bratislava",
          salary: 2400,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "13",
          name: "Vladimír",
          surname: "Urban",
          age: 44,
          mobile: "345678902",
          email: "vladimir.urban@example.com",
          adress: "Špitálska 15, Košice",
          salary: 3200,
          married: true,
          gender: "MALE",
        },
        {
          id: "14",
          name: "Gabriela",
          surname: "Jablonová",
          age: 26,
          mobile: "234567890",
          email: "gabriela.jablonova@example.com",
          adress: "Májová 8, Trnava",
          salary: 2100,
          married: false,
          gender: "FEMALE",
        },
        {
          id: "15",
          name: "Radovan",
          surname: "Danko",
          age: 42,
          mobile: "123456788",
          email: "radovan.danko@example.com",
          adress: "Zelená 33, Žilina",
          salary: 3100,
          married: true,
          gender: "MALE",
        },
      ] as Employee[],
    };
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
.wrapper {
  display: flex;
  justify-content: center;
  gap: 40px;
}
.form-container {
  width: 300px;
  margin: 25px auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 2px 2px 2px rgb(255, 255, 255);
}

.search-string {
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
}

label {
  font-weight: bold;
  margin-bottom: 5px;
}

input[type="text"],
select,
.checkbox {
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

input[type="text"]:focus,
select:focus,
.checkbox:focus {
  outline: none;
  border-color: #007bff;
}

input[type="checkbox"] {
  width: auto;
  margin-right: 8px;
}

button {
  padding: 10px 15px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background-color: #0056b3;
}
</style>
