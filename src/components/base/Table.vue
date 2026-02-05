<script setup>

</script>

<template>
  <div class="table">
    <div class="table__row first-entry">
      <div class="table__cell" data-cell="Регион"><span>Белгородская область</span></div>
      <div class="table__cell" data-cell="Название"><span>МБОУ Средняя общеобразовательная школа №2</span></div>
      <div class="table__cell" data-cell="Адрес"><span>ул. Николая Гондатти, д. 13 ул. Н. Гондатти 13 ; ул. Н. Зелинского 22</span></div>
      <div class="table__cell" data-cell="Уровни образования">
        <div class="table__tags">
          <span class="table__tag">Среднее</span>
          <span class="table__tag">Высшее</span>
          <span class="table__tag">Специальное</span>
          <span class="table__tag">Проф</span>
          <span class="table__tag">Бакалавр</span>
        </div>
      </div>
    </div>
    <div class="table__row">
      <div class="table__cell" data-cell="Регион"><span>Белгородская область</span></div>
      <div class="table__cell" data-cell="Название"><span>МБОУ Средняя общеобразовательная школа №65</span></div>
      <div class="table__cell" data-cell="Адрес"><span>ул. Николая Гондатти, д. 13 ул. Н. Гондатти 13 ; ул. Н. Зелинского 2002</span></div>
      <div class="table__cell" data-cell="Уровни образования">
        <div class="table__tags">
          <span class="table__tag">Среднее</span>
          <span class="table__tag">Высшее</span>
          <span class="table__tag">Специальное</span>
          <span class="table__tag">Проф</span>
          <span class="table__tag">Бакалавр</span>
        </div>
      </div>
    </div>
    <div class="table__row first-entry">
      <div class="table__cell" data-cell="Регион"><span>Брянская область</span></div>
      <div class="table__cell" data-cell="Название"><span>МБОУ Основная общеобразовательная школа №35</span></div>
      <div class="table__cell" data-cell="Адрес"><span>с. Засечное, ул. Изумрудная 8А</span></div>
      <div class="table__cell" data-cell="Уровни образования">
        <div class="table__tags">
          <span class="table__tag">Среднее</span>
          <span class="table__tag">Высшее</span>
          <span class="table__tag">Специальное</span>
          <span class="table__tag">Проф</span>
          <span class="table__tag">Бакалавр</span>
        </div>
      </div>
    </div>
    <div class="table__row ">
      <div class="table__cell" data-cell="Регион"><span>Брянская область</span></div>
      <div class="table__cell" data-cell="Название"><span>МБОУ Основная общеобразовательная школа №395</span></div>
      <div class="table__cell" data-cell="Адрес"><span>с. Засечное, ул. Изумрудная 8А</span></div>
      <div class="table__cell" data-cell="Уровни образования">
        <div class="table__tags">
          <span class="table__tag">Среднее</span>
          <span class="table__tag">Высшее</span>
          <span class="table__tag">Специальное</span>
          <span class="table__tag">Проф</span>
          <span class="table__tag">Бакалавр</span>
        </div>
      </div>
    </div>
    <div class="table__row">
      <div class="table__cell" data-cell="Регион"><span>Брянская область</span></div>
      <div class="table__cell" data-cell="Название"><span>МБОУ Основная общеобразовательная школа №935</span></div>
      <div class="table__cell" data-cell="Адрес"><span>с. Засечное, ул. Изумрудная 8А</span></div>
      <div class="table__cell" data-cell="Уровни образования">
        <div class="table__tags">
          <span class="table__tag">Среднее</span>
          <span class="table__tag">Высшее</span>
          <span class="table__tag">Специальное</span>
          <span class="table__tag">Проф</span>
          <span class="table__tag">Бакалавр</span>
        </div>
      </div>
    </div>

  </div>
</template>


<style scoped lang="scss">
.table {
  &__row {
    display: flex;
    flex-direction: column;
  }

  &__row + &__row {
    border-top: 2px solid #D3D3DE;
  }

  &__cell {
    @include font(14, 16);
    display: flex;
    align-items: center;
    padding: rem(6) rem(18);
  }

  &__tags {
    @include font(12, 14);
    display: flex;
    flex-wrap: wrap;
    gap: rem(4);
  }

  &__tag {
    padding: rem(4) rem(6);
    border: 1px solid #0E0E101A;
    border-radius: rem(8);
  }

  @include media-max($screen-sm-max) {
    &__cell {
      display: flex;
    }

    &__cell:first-child {
      padding-top: rem(14);
    }

    &__cell:last-child {
      padding-bottom: rem(14);
    }

    &__cell::before {
      @include font(12, 14);
      content: attr(data-cell) ':';
      padding-right: rem(12);
      width: rem(120);
      flex-basis: rem(120);
    }

    &__cell span {
      flex: 1;
    }
  }

  @include media-min($screen-md-min) {
    &__row {
      flex-direction: row;
    }

    &__row:not(.first-entry) &__cell:first-child {
      opacity: 0;
    }

    &__cell {
      flex: 1;
    }

    &__cell:last-child {
      flex-basis: 15%;
    }
  }

  @include media-min($screen-lg-min) {
    &__cell {
      flex-basis: 28%;
    }

    &__cell:last-child {
      flex-basis: rem(260);
    }
  }
}


</style>
