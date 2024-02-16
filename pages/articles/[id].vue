<template>
  <div class="Conteiner">
    <img src="/assets/images/img_2.png" alt="Описание картинки" />

    <h1>Бенуа — идеолог новой художественной эпохи</h1>

    <hr />

    <blockquote>
      «Этот образованный и чуткий человек всегда обладал, кроме того, одним
      качеством — страстью к педагогической деятельности. Он, будучи ещё совсем
      молодым человеком, невольно и беспрерывно «вwоспитывал» в своих верных
      собеседниках ту настоящую любовь к искусству, которою он непрестанно живёт
      до сих пор»
    </blockquote>

    <h4>Сергей Павлович Дягилев об Александре Николаевиче Бенуа.</h4>

    <hr />

    <p>
      В Петербурге в семье профессора архитектуры Николая Леонтьевича Бенуа и
      Камиллы Альбертовны Кавос 3 мая 1870 года родился сын — Александр Бенуа,
      которому было уготовано судьбою множество замечательных свершений.
    </p>

    <p>
      Семейная родословная Бенуа начинается с Никола Дени Бенуа, простого
      хлебопашца. Сын Никола, который приходился прадедом Александру Бенуа,
      получил образование самостоятельно и открыл школу, в которой получили
      образование пятеро его детей. Младший сын Никола, который приходился дедом
      будущему художнику, Луи-Жюль Бенуа, не смог принять революционных событий
      во Франции и в 1794 году приехал в Россию.
    </p>

    <img src="/assets/images/img_2.png" alt="Описание картинки" />
  </div>
</template>

<style scoped lang="scss">
.helper {
  outline: solid 1px red;

  & * {
    outline: solid 1px green;
  }

  > * {
    outline: solid 1px blue;
  }
}

.Conteiner {
  max-width: 950px;
  min-width: 320px;
  @apply p-4 md:px-6 lg:px-0 m-auto;
}

img {
  @apply w-full rounded-lg;
}

h1 {
  @apply font-bold text-lg my-7 text-center;
  @apply sm:text-4xl;
}

h4 {
  @apply text-sm my-2.5 text-center;
}

hr {
  @apply w-1.5 h-1.5 bg-gray-300 rounded-full mx-auto my-7;
  @apply sm:w-1/12 sm:h-px;
}

blockquote {
  @apply w-11/12 m-auto italic font-bold text-center;
  @apply sm:w-4/5 sm:text-xl;
}

p {
  @apply text-sm mb-7 mx-auto;
  @apply sm:w-11/12 sm:text-base;
}
</style>
