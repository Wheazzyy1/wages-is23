<script setup>

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
        <input type="date" v-model="name" class="form-control" :class="{'is-invalid': !date}" id="date">
        <div class="invalid-feedback">
        Заполните дату выдачи з/п!
      </div>
    </div>
    <div class="mb-3">
        <label for="day" class="form-label">Количество отработанных дней</label>
        <input type="text" v-model="name" class="form-control" :class="{'is-invalid': !day}" id="day">
        <div class="invalid-feedback">
        Введите количество отработанных дней!
      </div>
    </div>
    <div class="mb-3">
        <label for="allmoney" class="form-label">Размер заработной платы</label>
        <input type="text" v-model="name" class="form-control" :class="{'is-invalid': !allmoney}" id="allmoney">
        <div class="invalid-feedback">
        Введите размер заработной платы
      </div>
    </div>
    <button type="button" class="btn btn-outline-success">Добавить</button>
    </div>
  </div>
</div>
</template>

