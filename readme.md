## Шпаргалка по SCSS

- [Переменные](#Переменные)
- [Вложенность](#Вложенность)
- [Импорт файлов](#Импорт-файлов)
- [Миксины](#Миксины)
- [Extend](#Extend)
- [Математические операции](#Математические-операции)
- [Условные выражения](#условные-выражения)
- [Функции](#функции)

### Переменные

```scss
$font-size: 14px;
$font-color: #f0f0f0;
$string: 100%/10;

p {
  font-size: $font-size;
  line-height: $font-size * 2;
  color: $font-color;
}
```

[назад](#Шпаргалка-по-SCSS)

### Вложенность

```scss
.class {
  font-size: 10px;

  .span {
    font-size: 20px;
  }
}

.block {
  display: block;

  &-element {
    font-size: 20px;

    &-mod {
      font-size: 30px;
    }

    &::before {
      content: "";
    }
  }
}
```

[назад](#Шпаргалка-по-SCSS)

### Импорт файлов

```scss
@import "file-for-import";
```

[назад](#Шпаргалка-по-SCSS)

### Миксины

```scss
@mixin font-style($fz, $color) {
  font-family: Arial, sans-serif;
  font-size: $fz;
  line-height: $fz * 1.5;
  color: $color;
}

h1 {
  @include font-style($font-size, #000);
}

h2 {
  @include font-style($font-size * 2, #000);
}
```

[назад](#Шпаргалка-по-SCSS)

### Extend

```scss
.lh {
  line-height: 2;
}

h1 {
  font-size: 10px;
  @extend .lh;
}

h2 {
  font-size: 8px;
  @extend .lh;
}
```

[назад](#Шпаргалка-по-SCSS)

### Математические операции

```scss
.math {
  font-size: 14px * 2;
  width: 100% / 12 * 4;
}
```

[назад](#Шпаргалка-по-SCSS)

### Условные выражения

```scss
@mixin color($status) {
  @if $status == error {
    color: red;
  } @else if $status == ok {
    color: green;
  } @else {
    color: black;
  }
}

.alert {
  font-size: 12px;
  padding: 20px;
  @include color(errordgf);
}
```

[назад](#Шпаргалка-по-SCSS)

### Функции

```scss
@function column-width($number) {
  @return 100% / 12 * $number;
}

@for $i from 1 to 12 {
  .col-#{$i} {
    width: column-width($i);
  }
}

.column {
  width: column-width(4);
}
```

[назад](#Шпаргалка-по-SCSS)
