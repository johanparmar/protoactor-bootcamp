# Урок 1: Зачем использовать модель акторов?

Итак, почему мы должны использовать модель акторов в нашем приложении? Использование модели акторов упрощает создание масштабируемых, конкурентных обладающих высокой пропускной способностью и низкой задержкой приложений.

Таким образом, если вам требуется создать приложение, обладающее одним или несколькими из перечисленных свойств, модель акторов может быть подходящим решением для вас.

Поэтому давайте углубимся в подробности о том, почему нам может понадобиться использовать модель акторов и платформу Proto.Actor.

### Никакого ручного управления потоками.

Прежде всего, если мы создаём конкурентное приложение с использованием модели акторов нам больше не нужно управлять потоками вручную. И мы можем быть уверены, что наш код потокобезопасен. Теперь вместо того, чтобы использовать блокировки для общих ресурсов, мы используем модель актора, чтобы нам не приходилось делать эту склонную к ошибкам и сложную работу вручную.

### Высокий уровень абстракции.

Используя модель акторов, мы получаем высокий уровень абстракции. Поскольку все в нашем приложении будет рассматриваться как акторы.

Когда мы хотим, чтобы один актор взаимодействовал с другим актором, мы делаем это через отправку сообщений. Вы можете рассматривать модель акторов как объектное ориентированное программирование на стероидах. Так как модель акторов формализует взаимодействие между объектами посредством отправки сообщений.

### Вертикальная-масштабируемость системы (scale-up).

Так как модель акторов управляет конкурентностью за нас, мы можем с легкостью увеличивать вычислительные мощности, на которых запушено наше приложение. К примеру. Если мы добавим дополнительные процессоры или оперативную память к нашему серверу, модель актров автоматически масштабируется и задействует дополнительные ресурсы без изменения исходного кода приложения. Так же нам не потребуется вручную управлять потоками и блокировками.

### Горизонтальная-масштабируемость системы (scale-out).

Благодаря модели акторов в дополнении к вертикальной-масштабируемости, где мы добавляем вычислительные ресурсы к локальному серверу, мы можем использовать горизонтальную-масштабируемость. Где мы распределяем нашу задачу на несколько физических серверов.

### Отказоустойчивость и обработка ошибок (Fault tolerance and error handling).

Когда мы используем модель акторов в нашем приложении, мы получаем преимущество отказоустойчивости и обработки ошибок из коробки. 

В этом курсе мы увидим как Proto.Actor фактически изолирует ошибки в определённой части иерархии акторов, а если, возникают ошибки, с которыми невозможно справиться, мы можем просто перезапустить эти акторы, чтобы создать систему самовосстановления.

### Общая архитектура.

Наконец. Используя модель акторов для представления нашей системы. Мы говорим на общем языке. Таким образом, вместо того, чтобы рассуждать о множестве различных способов делать одни и те же вещи в рамках приложения, мы просто должны изучить способ делать эти вещи с помощью модели акторов и придерживаться их.

### Отличная работа! Переходим к уроку №2 !

Здорово! Поздравляем с завершением первого урока!

**Переходим к [Уроку 2 - Создание и обработка различных типов сообщений](https://github.com/mungobungo/akka-bootcamp-translation-ru/blob/feature/lesson_1-5/src/Unit-1/lesson2).**