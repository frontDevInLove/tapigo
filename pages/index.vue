<template>
  <div class="max-w-4xl mx-auto px-4 py-8">
    <p class="mb-4 text-lg text-gray-700">
      Установить (активировать) внутри Windows ядро линукса WSL 2 (если
      используется Windows) и на него установить Ubuntu 22. Для Unix систем
      использовать стандартное файловое дерево.
    </p>

    <p class="mb-4 text-lg text-gray-700">
      Создать Nuxt проект по пути /var/www/tapigo/test/
    </p>

    <p class="mb-4 text-lg text-gray-700">
      Реализовать три страницы на компонентах и по правилам шаблонизатора Nuxt:
    </p>

    <ul class="list-disc pl-8 mb-4">
      <li class="mb-2 text-gray-700">
        Форма с отправкой данных ФИО, номер телефона, почта, пароль (ссылку в
        запрос можно не указывать, главное реализовать метод) с использованием
        Tailwind + добавить валидацию на поля ФИО (только кириллица и 2 слова) и
        номер телефона (начинается с +7);
      </li>
      <li class="mb-2 text-gray-700">
        Адаптивный макет с использованием Tailwind (ссылка ниже);
      </li>
      <li class="mb-2 text-gray-700">
        Страница (статья), состоящая из нескольких абзацев (ссылка ниже) на
        ванильном CSS, используя каскадность, а также связь ванильного CSS и
        Tailwind (через @apply) внутри Nuxt проекта;
      </li>
    </ul>

    <p class="mb-4 text-lg text-gray-700">
      Во всей верстке обязательна семантика в потоке документа. Готовое задание
      разместить публичным репозиторием на Github и прислать ссылку на этот
      репозиторий (очень просим проверить доступность и корректность ссылки на
      репозиторий).
    </p>

    <p class="mb-4">
      <a
        href="https://www.figma.com/file/xr4QN6eE3LmeyukF7VhwAF/test-EX?type=design&node-id=0-1&mode=design&t=Rc0jZEJ9lhpWHBSP-0"
        target="_blank"
        class="text-blue-500 hover:text-blue-700 underline"
        >Адаптивный макет</a
      >
    </p>

    <p>
      <a
        href="https://journal.tapigo.ru/articles/benua-ideolog-novoi-xudozestvennoi-epoxi"
        target="_blank"
        class="text-blue-500 hover:text-blue-700 underline"
        >Пример статьи</a
      >
    </p>
  </div>
</template>
