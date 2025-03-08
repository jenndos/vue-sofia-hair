<template>
  <div class="table-responsive">
    <table class="table-prices">
      <thead>
        <tr>
          <th>Длина волос</th>
          <th>Кератиновое выпрямление / Ботокс для волос</th>
          <th>Нанопластика</th>
          <th>Многоступенчатое холодное восстановление</th>
          <th>Уход за натуральными и окрашенными волосами</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>До плеч<br />(15-25см)</td>
          <td>3500</td>
          <td>4000</td>
          <td>2500</td>
          <td>2000</td>
        </tr>
        <tr>
          <td>Ниже плеч<br />(30-35см)</td>
          <td>4000</td>
          <td>4500</td>
          <td>3000</td>
          <td>2500</td>
        </tr>
        <tr>
          <td>По лопатки<br />(40-45см)</td>
          <td>5000</td>
          <td>5500</td>
          <td>4000</td>
          <td>3500</td>
        </tr>
        <tr>
          <td>Ниже лопаток<br />(50-55см)</td>
          <td>5500</td>
          <td>6000</td>
          <td>4500</td>
          <td>4000</td>
        </tr>
        <tr>
          <td>По талию<br />(60-65см)</td>
          <td>6500</td>
          <td>7000</td>
          <td>5500</td>
          <td>5000</td>
        </tr>
        <tr>
          <td>По пояс<br />(70-75см)</td>
          <td>7000</td>
          <td>7500</td>
          <td>6000</td>
          <td>5500</td>
        </tr>
        <tr>
          <td>Ниже пояса<br />(80-85см)</td>
          <td>7500</td>
          <td>8000</td>
          <td>6500</td>
          <td>6000</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
/* Container to enable horizontal scrolling on small devices */
.table-responsive {
  width: 100%;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}

/* Ensure the table expands and is scrollable if necessary */
.table-prices {
  border-collapse: collapse;
  width: 100%;
  min-width: 666px; /* fallback width to maintain table layout */
}

.table-prices td,
.table-prices th {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: center;
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
  color: #fff;
}

/* Optional: Adjust styles for smaller screens */
@media (max-width: 600px) {
  .table-prices td,
  .table-prices th {
    padding: 6px;
    font-size: 14px;
  }
}
</style>
