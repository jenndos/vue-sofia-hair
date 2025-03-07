<template>
  <table class="table-prices">
    <thead>
      <tr>
        <th>Длина волос</th>
        <th>Холодное восстановление</th>
        <th>Нанопластика</th>
        <th>Кератиновое выпрямление / Ботокс для волос</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>До плеч</td>
        <td>2500</td>
        <td>3500</td>
        <td>3000</td>
      </tr>
      <tr>
        <td>До лопаток</td>
        <td>3000</td>
        <td>3500</td>
        <td>4000</td>
      </tr>
      <tr>
        <td>До середины спины</td>
        <td>3500</td>
        <td>4000</td>
        <td>4500</td>
      </tr>
      <tr>
        <td>До локтей</td>
        <td>4000</td>
        <td>4500</td>
        <td>5000</td>
      </tr>
      <tr>
        <td>До ягодиц</td>
        <td>4500</td>
        <td>5000</td>
        <td>5500</td>
      </tr>
      <tr>
        <td>Ниже</td>
        <td>5000</td>
        <td>5500</td>
        <td>6000</td>
      </tr>
    </tbody>
  </table>
</template>

<script setup lang="ts"></script>

<style scoped>
.table-prices {
  border-collapse: collapse;
  max-width: 666px;
}

.table-prices td,
.table-prices th {
  border: 1px solid #ddd;
  padding: 8px;
}

.table-prices tr:nth-child(even) {
  background-color: #f2f2f2;
}

.table-prices tr:hover {
  background-color: #e9e9e9;
}

.table-prices th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: center;
  background-color: #3b3b3b;
  color: rgb(255, 255, 255);
  /*font-weight: 500;*/
}
</style>
