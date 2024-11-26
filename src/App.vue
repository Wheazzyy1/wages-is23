<script setup>
    import { ref, computed } from "vue";
const employees = ref([
{
  id: 1,
  name: 'Шекшаев Максим Леонидович',
  date: '24.11.2024',
  count: 20,
  pay: 1000,
  payNalog: 850,
},
{
  id: 2,
  name: 'Иванов Андрей Максимович',
  date: '20.11.2024',
  count: 15,
  pay: 750,
  payNalog: 887.5,
},
{
  id: 3,
  name: 'Летучий Алексей Алексеевич',
  date: '24.11.2024',
  count: 10,
  pay: 500,
  payNalog: 425,
},
]);
const name = ref('');
const date = ref('');
const day = ref('');
const allmoney = ref('');
 
//  const name = ref('');
//  const date = ref('');
//  const day = ref(1);
//  const allmoney = ref(0);

//  const addzp = () => {
//   if(name.value && date.value && day.value && allmoney.value) {
//  zps.value.push({
//   id: Date.now(),
//    name:name.value,
//    date: date.value,
//    day:day.value,
//    allmoney:allmoney.value,
//  });
//   }
// }

// const removezp = (id) => {
//   zps.value = zps.value.filter((zp) => zp.id !=id);
// }

// const totalSum = computed(() => {
//   return zps.value.reduce((sum, zp) => sum + (product.allmoney * product.day), 0 )
// });
</script>

<template>
  <div class="container">
    <div class="row">
    <div class="col">
      <h1 class="text-center my-3"></h1>
      <div class="mb-3">
        <label for="name" class="form-label">ФИО</label>
        <input type="text" v-model="name" class="form-control" :class="{'is-invalid': !name}" id="name">
        <div class="invalid-feedback">
        Введите ваше ФИО!
      </div>
    </div>
    <div class="mb-3">
        <label for="date" class="form-label">Дата выдачи зарплаты</label>
        <input type="date" v-model="date" class="form-control" :class="{'is-invalid': !date}" id="date">
        <div class="invalid-feedback">
        Заполните дату выдачи з/п!
      </div>
    </div>
    <div class="mb-3">
        <label for="day" class="form-label">Количество отработанных дней</label>
        <input type="text" v-model="day" class="form-control" :class="{'is-invalid': !day}" id="day">
        <div class="invalid-feedback">
        Введите количество отработанных дней!
      </div>
    </div>
    <div class="mb-3">
        <label for="allmoney" class="form-label">Размер заработной платы</label>
        <input type="text" v-model="allmoney" class="form-control" :class="{'is-invalid': !allmoney}" id="allmoney">
        <div class="invalid-feedback">
        Введите размер заработной платы
      </div>
    </div>
    <button @click="addzp" type="button" class="btn btn-outline-success">Добавить</button>
    </div>
  </div>
  <div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col" v-for="employee in employees" :key="employee.id">
    <div class="card h-100">
     
      <div class="card-body">
        <h5 class="card-title">Ф.И.О. сотрудника:</h5>
       <p class="card-text "> {{ employee.name }}</p>
       <h5 class="card-title">Дата выдачи зарплаты:</h5>
        <p class="card-text">{{employee.date}}</p>
        <h5 class="card-title">Количество отработанных дней:</h5>
        <p class="card-text">{{employee.count }}</p>
        <h5 class="card-title">Размер заработной платы сотрудника без налоговых отчислений:</h5>
        <p class="card-text">{{employee.pay}}$</p>
        <h5 class="card-title">Размер заработной платы сотрудника с налоговыми отчислениями (-15%):</h5>
        <p class="card-text">{{ (employee.pay * 0.85).toFixed(2) }}$</p>
      </div>
      <div class="card-footer text-end">
        <button @click="removeEmp(employee.id)" class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </div>
  </div>
</div>

</template>

