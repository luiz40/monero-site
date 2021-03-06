---
tags: ["kovri"]
terms: ["Message", "Messages", "сообщений", "сообщениями", "сообщения", "сообщение", "соoбщениям", "сообщению"]
summary: "Механизмы, в которых информация перемещается в I2P"
---

### Основная информация

*Сообщения* (на верхнем уровне @транспортного протокола) содержат различные типы информации, необходимой сети, но, что более важно, всё, что вы видите, делаете, отправляете или получаете принимает форму и становится *сообщениями*.

В @I2P существует 2 важных типа @сообщений:

- @туннельные сообщения
- @I2NP сообщения

Преимущественно *@туннельные сообщения* **содержат фрагменты** @I2NP сообщений, которые затем [собираются](https://geti2p.net/en/docs/tunnels/implementation) заново в определённых точках @туннеля.

### Углублённая информация

@I2NP сообщения имеют близкое отношение к @туннeльным @соoбщениям, поэтому легко неправильно интерпретировать термин *"сообщения"*, когда читаешь спецификации @Java-I2P:

>
1. Во-первых, в шлюзе туннеля накапливаются и проходят предварительную обработку ряд I2NP сообщений для последующей передачи в туннель для доставки.
2. Затем шлюз шифрует данные, прошедшие предварительную обработку, и направляет их на первый транзитный участок.
3. Одноранговый узел и последующие участники туннеля снимают уровень шифрования, проверяя, не дублируется ли он, а затем направляют сообщение следующему одноранговому узлу.
4. В конечном счёте туннельные сообщения прибывают в конечную точку, где I2NP сообщения связываются шлюзом и собираются заново, после чего направляются в соответствии с запросом.

### Примечания

- @I2NP @сообщения необходимо фрагментировать, поскольку они имеют различный размер (от 0 до почти 64 KB), а @туннельные @сообщения имеют фиксированный размер
- Подробную информацию и спецификации можно найти на страницах [спецификаций I2NP](https://geti2p.net/spec/i2np) и [спецификаций туннельных сообщений](https://geti2p.net/spec/tunnel-message)
