# Підсили свою атаку у 100 разів разом із db1000nX100

**db1000nX100** це Linux контейнер для популярної програми
[*db1000n*](https://github.com/Arriven/db1000n), щo дозволяє значно підняти
ефективність атаки, та вирішити ще цілу низку проблем.

Якщо уявити що [*db1000n*](https://github.com/Arriven/db1000n) – це “бомба”. То
*db1000nX100* – це “засоби доставки” великої кількості бомб одночасно.

Як відомо, основний метод боротьби із DDoS атаками – це фільтрування за IP
адресою. Ті ІР-адреси, що здійснюють багато запитів, починають блокуватися. Тому
для успішної атаки потрібно залучати якомога більше різних ІР-адрес.

Саме цим і займається *db1000nX100*. Засіб автоматично встановлює багато
паралельних VPN підключень, на кожному із яких працює окрема
[*db1000n*](https://github.com/Arriven/db1000n). Раз у 15 хвилин всі VPN
з’єднання від’єднуються, і система заново встановлює з’єднання уже через інші
сервери. Таким чином постійно змінюються проміжні сервери (ІР) звідки ведеться
атака.

Звісно, що для такого виду атаки потрібно купити підписку на декілька VPN
провайдерів. Але це не дуже дорого, підписка на 1 місяць на VPN коштує в
середньому 300 гривень.

Якщо задіяти низку VPN провайдерів, та комп’ютер зі 6 CPU ядрами і 16+GiB
оперативної пам’яті, то система виходить на 100+ одночасних VPN підключень.
Тобто [*db1000n*](https://github.com/Arriven/db1000n) атакує одночасно через
100+ різних ІР-адрес. Звідси і назва проекту **Х100**.

*db1000nX100* не є звичайною програмою, яку потрібно запустити. Це контейнер,
котрий доступний у двох варіантах: під *Oracle Virtual Box*, та під *Docker*.
Фактично користувач запускає перевірну і безпечну *Oracle Virtual Box* чи
*Docker*. А вже ними опрацьовується контейнер із *db1000nX100*. Вміст контейнеру
працює в ізольованому від основної операційної системи середовищі – тому це
знижує до 0 шанси інфікувати Ваш комп’ютер вірусом. Звісно, у *db1000nX100*
немає вірусів. Але навіть суто теоретично, пробити контейнер та інфікувати
операційну систему не реально.

Ще одною перевагою *db1000nX100* є те, що всі VPN підключення відбуваються
всередині контейнера. Але Вам не потрібно підключати весь комп’ютер через VPN
(що зазвичай призводить до сповільнення інтернету, і зниження комфорту Вашої
роботи)
