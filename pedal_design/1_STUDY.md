## 1. Исследование
### Теоретическая часть
Педаль (или примочка) – электронное устройство для обработки и преобразования сигнала, звука музыкального инструмента. Педали делятся на аналоговые (транзисторные или ламповые) и цифровые.

Довольно сложно найти теоретическую информацию по этой теме, т.к. все (базовые) примочки имеют довольно простые составляющие, а структура их определяется типом эффекта. 
В основном в педалях используются резисторы, конденсаторы, транзисторы, диоды и потенциометры. 
Из резисторов и конденсаторов составляются фильтры, транзисторы и диоды преобразуют сигналы, к потенциометрам прикрепляются ручки для управления характеристиками педали. 
В более навороченных примочках можно найти операционные усилители.

В сети преимущественно представлены пошаговые инструкции к сборке, без подробных пояснений что к чему. 
В следствие чего, предлагаю в рамках изучения темы пособирать различные педали в Multisim и поэкспериментировать с ними, постепенно рассматривая все более сложные схемы.

Стоит отметить, что большинство примочек питается от 9 В. А также, что рассматриваемые примочки – гитарные, т.е. генераторы сигналов должны работать с напряжением от 100 мВ до 1 В и частотой от 80 до 1100 Гц.
По умолчанию буду использовать 500 мВ и 550 Гц, если не укажу иначе.

### Дисторшн

Рассматриваемая схема взята отсюда [Откуда берется "дж-дж". Разбираемся, как устроен и работает гитарный эффект перегруза](https://pikabu.ru/story/otkuda_beretsya_dzhdzh_razbiraemsya_kak_ustroen_i_rabotaet_gitarnyiy_yeffekt_peregruza_9903964)
Пост очень хороший, все ясно и наглядно и схема нетрудная.

Вот такая схема получилась. (В отличие от оригинальной схемы, тут отсуствует свитч на C3)
<p align="center" ><img width="1320" height="677" alt="image" src="https://github.com/user-attachments/assets/d9b92e13-3128-423e-946d-4b388d85ce00" /></p>
<p align="center" >Схема педали дисторшн</p>

Посмотрим, как будет выглядить выходной сигнал при разных значениях потенциометров R4 и R5 соотстветственно

<p align="center" ><img width="303" height="229" alt="image" src="https://github.com/user-attachments/assets/877d8c8d-f764-4704-99e7-8792da93d68b" />
  <img width="303" height="233" alt="image" src="https://github.com/user-attachments/assets/3032bc0e-61d3-4607-a1f4-d4a4d2fc46c2" /></p>
<p align="center" >1) 50%, 50% 2) 50%, 95% </p>

<p align="center" ><img width="303" height="231" alt="image" src="https://github.com/user-attachments/assets/6a03c6e5-81a1-4a2b-b435-19554bd07ed1" />
  <img width="303" height="230" alt="image" src="https://github.com/user-attachments/assets/551890b5-2464-40a0-b84c-83f1713bed6e" /></p>
<p align="center" >3) 50%, 5% 4) 5%, 50% </p>

<p align="center" ><img width="305" height="231" alt="image" src="https://github.com/user-attachments/assets/431d9b01-65a5-434e-9d45-ed6f881115a0" />
<img width="303" height="231" alt="image" src="https://github.com/user-attachments/assets/98227856-dc05-4f44-b4b2-eb1f06b8aafe" /></p>
<p align="center" >5) 95%, 50% 6) 5%, 5% </p>

Видно, что R4 влияет на "скругленность", а R5 на амплитуду выходного сигнала. Теперь, попробуем поизменять значения резисторов и конденсаторов (после снятия показаний буду возвращать их к изначальному значению).

<p align="center"><img width="306" height="233" alt="image" src="https://github.com/user-attachments/assets/d089a2d8-2be0-45fb-b7fc-7f48cabe0bcc" /></p>
<p align="center"> C3 с 22 нФ на 100 нФ</p>

<p align="center"><img width="307" height="237" alt="image" src="https://github.com/user-attachments/assets/dc9c0c56-17f5-4561-8d8f-5cf5f8ae6eea" /></p>
<p align="center">уберем С3 из цепи</p>

<p align="center"><img width="311" height="234" alt="image" src="https://github.com/user-attachments/assets/2b1e6155-0f0a-45d4-9fb0-1ea1d11fc619" /></p>
<p align="center">уберем С2 с 100 нФ до 1 нФ</p>

<p align="center"><img width="305" height="230" alt="image" src="https://github.com/user-attachments/assets/c16cf8b8-8ae6-4970-bf92-b21d48d2a950" /></p>
<p align="center">уберем C2 из цепи</p>

Чем больше емкость на C3, тем дольше он заряжается, соотвественно превращая сигнал в пилу. Видно, что от емкости C2 зависит амплитуда.

<p align="center"><img width="305" height="231" alt="image" src="https://github.com/user-attachments/assets/f76dfac0-f726-47f5-b968-44663331f506" /><img width="183" height="158" alt="image" src="https://github.com/user-attachments/assets/21aea072-8b8f-4515-bbc5-471df40defa7" /></p>
<p align="center">Сонаправим диоды вниз</p>

<p align="center"><img width="307" height="232" alt="image" src="https://github.com/user-attachments/assets/8962e1be-e45f-43c2-8b05-392ece76a014" /><img width="176" height="155" alt="image" src="https://github.com/user-attachments/assets/aecfb094-310e-4064-b91e-2fde2d354d3d" /></p>
<p align="center">Сонаправим диоды вверх</p>

<p align="center"><img width="305" height="229" alt="image" src="https://github.com/user-attachments/assets/2ee33201-54f5-43a5-9ad3-abc794d94bbe" /></p>
<p align="center">уберем диоды из цепи</p>

<p align="center"><img width="306" height="232" alt="image" src="https://github.com/user-attachments/assets/6f556835-5006-407b-a11a-4b81ca85e711" /><img width="309" height="236" alt="image" src="https://github.com/user-attachments/assets/726c7cee-307d-4ca8-9381-52307aa110b9" /></p>
<p align="center">уберем D2, уберем D1</p>

Диоды сонаправленные вниз увеличивают ток в цепи, т.к. они соединены параллельно, и, что логично было бы предположить, увеличивается амплитуда. Почему амплитуда увеличивается во всех остальных случаях я не понимаю :(
Может там вообще происходит что-то не хорошее, а я этого не вижу. Ну если разберусь, сделаю апдейт.

<p align="center"><img width="306" height="232" alt="image" src="https://github.com/user-attachments/assets/56f7612d-b150-4a2a-961c-c76260c9f0d9" /></p>
<p align="center">R1 с 680 Ом до 680 мОм</p>

<p align="center"><img width="307" height="233" alt="image" src="https://github.com/user-attachments/assets/2afd97ca-72d9-4b2f-9e8a-a3ce060c5513" /><img width="311" height="232" alt="image" src="https://github.com/user-attachments/assets/8da1abc1-006f-418a-a531-db297f984da6" /></p>
<p align="center">R1 с 680 Ом до 3500 Ом, до 5000 О</p>

Чем меньше сопротивление на эмиттере, тем более "мощный" срез сигнала получается.

Ну а на входе находится ФВЧ, и транзистор – усилительный каскад.

Форма входного сигнала особо не влияет на выход, картина на осциллогафе остается той же.

### Фуз
coming soon
