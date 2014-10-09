---
layout: default
title: Метод Friends.GetRequests
permalink: friends/getRequests/
comments: true
---
# Метод Friends.GetRequests
Возвращает информацию о полученных или отправленных заявках на добавление в друзья для текущего пользователя.

## Синтаксис
```csharp
public ReadOnlyCollection<long> GetRequests(int? count = null, int? offset = null, bool extended, bool needMutual, bool out, bool sort, bool suggested)
```

## Параметры
+ **count** - максимальное количество заявок на добавление в друзья, которые необходимо получить (не более 1000).
+ **offset** - смещение, необходимое для выборки определенного подмножества заявок на добавление в друзья.
+ **extended** - определяет, требуется ли возвращать в ответе сообщения от пользователей, подавших заявку на добавление в друзья. И отправителя рекомендации при suggested=true.
+ **needMutual** - определяет, требуется ли возвращать в ответе список общих друзей, если они есть. Обратите внимание, что при использовании need_mutual будет возвращено не более 20 заявок.
+ **out** - false — возвращать полученные заявки в друзья (по умолчанию), true — возвращать отправленные пользователем заявки.
+ **sort** - false — сортировать по дате добавления, true — сортировать по количеству общих друзей. (Если out = true, данный параметр не учитывается).
+ **suggested** - true — возвращать рекомендованных другими пользователями друзей, false — возвращать заявки в друзья (по умолчанию).

## Результат
+ Если не установлен параметр need_mutual, то в случае успеха возвращает отсортированный в антихронологическом порядке по времени подачи заявки список идентификаторов (id) пользователей (кому или от кого пришла заявка).
+ Если установлен параметр need_mutual, то в случае успеха возвращает отсортированный в антихронологическом порядке по времени подачи заявки массив объектов, содержащих информацию о заявках на добавление в друзья. Каждый из объектов содержит поле uid, являющийся идентификатором пользователя. При наличии общих друзей, в объекте будет содержаться поле mutual, в котором будет находиться список идентификаторов общих друзей.
## Исключения

## Пример
```csharp
// TODO: 
```