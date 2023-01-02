<script lang="ts" setup>
  const classBlockColor = (x: number, y: number): string => {
  }
</script>

<template>
  <h1>プレイ画面</h1>
  <h2>ユーザー名: {{ $route.query.name }}</h2>
  <h2>ユーザー名: </h2>
  <div class="container">
    <table class="field" style="border-collapse: collapse">
      <tr
        v-for="(row, y) in field"
        :key="y">
        <td
          class="block"
          v-for="(col, x) in row"
          :key="() => `${x}${y}`"
          :class="classBlockColor(x, y)"
        />
      </tr>
    </table>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    display: flex;
    justify-content: center;
    align-items: stretch;
  }
 
  .field {
    border-collapse: collapse;
    border: ridge 0.4em #2c3e50;
    border-top: none;
  }
 
  .block {
    width: 2em;
    height: 2em;
    border: 0.1px solid #95a5a6;

    &-i {
      background: #3498db;
    }
    &-o {
      background: #f1c40f;
    }
    &-t {
      background: #9b59b6;
    }
    &-j {
      background: #1e3799;
    }
    &-l {
      background: #e67e22;
    }
    &-s {
      background: #2ecc71;
    }
    &-z {
      background: #e74c3c;
    }
  }
</style>
