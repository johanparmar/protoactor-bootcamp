# Proto.Actor Bootcamp - Модуль 9: Хранимые акторы.

<img src="images/protowhite.png" alt="protowhite" style="float: left; zoom: 20%;" />

## Концепции, с которыми вы познакомитесь.

Состояние актора, хранящееся в оперативной памяти, теряется, когда актор останавливается или перезапускается или когда останавливается или перезапускается вся система акторов. В этой главе мы расскажем, как обеспечить сохранность этого состояния с помощью модуля Proto.Persistence.

Очень часто для создания, извлечения, изменения и удаления записей используются базы данных (эти операции также называют СRUD операциями). Записи в базе данных нередко используются для хранения текущего состояния системы. В этом случае база данных действует как контейнер.

Для организации хранения состояния в Proto.Actor используется технология под названием Event Sourcing (историясо бытий), и ей будет посвящён первый раздел этого модуля. В нем вы узнаете, как можно хранить изменения состояний в виде последовательности не изменяемых событий в журнале базы данных.

Затем мы займемся исследованием хранимого актора PersistentActor. Хранимый актор упрощает запись своего состояния в виде событий и его восстановление после аварии или перезапуска.

Модули Proto.Cluster и Proto.Persistence можно использовать вместе для создания кластерных приложений, которые продолжают нормальную работу даже после аварии или замены нескольких узлов.

Но сначала займемся историей событий (Event Sourcing), технологией, лежащей в основе механизма хранения в Proto.Persistence.

#### Когда может понадобиться восстанавливать состояние актора?

Заметим сразу, что нет смысла делать каждый актор хранимым только потому, что это возможно. Когда же действительно следует обеспечивать сохранность состояния актора? Это во многом зависит от требований к системе и особенностей взаимодействий других систем с акторами.

Актор, жизненный цикл которого длится дольше, чем требуется для обработки одного сообщения, и который накапливает ценную информацию с течением времени, часто требует долговременного хранения состояния. Акторы такого рода обладают идентичностью - некоторым идентификатором, посредством которого к такому актору можно обратиться позднее. Примерам может служить актор корзины покупателя; пользователь переходит между разделами веб-магазина в поисках нужных товаров, добавляет товары в корзину и удаляет их оттуда. Было бы неправильно показывать пустую корзину после неожиданной аварии или перезапуска актора. Другой случай - когда множество систем посылают сообщения актору, моделирующему конечный автомат согласования сообщений между системами. Актор может запоминать получаемые сообщения и конструировать некоторый контекст для окружающих систем. Примерам может служить система, получающая заказы с веб-сайта и координирующая процесс получения товаров со склада, их доставку и учет путем интеграции с несколькими существующими службами. В случае перезапуска актор должен продолжить работу с последнего известного правильного состояния, чтобы подключённые системы могли продолжить работу в требуемом порядке.

Это лишь несколько примеров, когда необходимо обеспечить сохранность состояния актора. Не нужно стараться обеспечить сохранность состояния, если актор выполняет всю работу от начала до конца в ходе обработки единственного сообщения. Примерам может служить актор, который обрабатывает НТТР-запросы, не имеющие состояния и содержащие всю необходимую информацию. В этом случае, если произойдёт сбой, клиент может просто повторить НТТР-запрос.

## Оглавление

1. [Что такое Event Sourcing.](lesson-1/README.md)
2. [Хранимые акторы.](lesson-2/README.md)
3. [Снимки состояний.](lesson-3/README.md)

