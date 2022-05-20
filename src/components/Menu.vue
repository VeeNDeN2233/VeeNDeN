   <template>
  <div class="originWindow">
    <div class="headerWindow">
      <button class="btnWindowExit"></button>
    </div>
    <div class="halloText">
      Безусловно, все те кто общается с ОС Linux хоть раз да имели дело(во
      всяком случае слышали точно) с командной оболочкой BASH. Но BASH не только
      командная оболочка, это еще и превосходный скриптовый язык
      программирования. Цель этой статьи — познакомить поближе юзеров с bash,
      рассказать про синтаксис, основные приемы и фишки языка, для того чтобы
      даже обычный пользователь смог быстренько написать простой скрипт для
      выполнения ежедневной(-недельной, -месячной) рутинной работы или, скажем,
      «на коленке» наваять скриптик для бэкапа директории.
    </div>

    <div class="terminal">
      <div id="history"></div>
      <div class="line">
        <span id="path">c:/&nbsp;>&nbsp;</span>
        <input type="text" id="input" />
      </div>
    </div>
    <a href="" class="run">run</a>
  </div>
</template>