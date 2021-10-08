<script>
export default {
  name: 'List',
}
</script>

<template>
<div class="news-list">
    <div class="wrapper">
        <div class="news-list-inner">
            <table>
                <tr>
                    <th>Номер новости</th>
                    <th>Название</th>
                </tr>
                <tr>
                    <td>1</td>
                    <td>Вышло обновление Vue 3</td>
                </tr>
            </table>
        </div>
    </div>
</div>
</template>

<style scoped>
*, *:after, *:before {
  margin: 0;
  padding: 0;  
}

.wrapper {
  max-width: 1280px;
  margin: 0 auto;
}