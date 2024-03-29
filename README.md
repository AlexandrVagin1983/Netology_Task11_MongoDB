# Домашнее задание к занятию «2.5 База данных и хранение данных»

**Задание 2:** 
* запрос(ы) для *вставки* данных минимум о двух книгах в коллекцию **books**:\
await db.collection('books').insertMany([\
>  {\
>>    id: 'dce5ccf7-f598-4843-9284-8f9a8dd17903А'\
>>    title: 'Сборник задач по физике.',\
>>    description: 'Задачи по физике для учащихся 9 классов.',\
>>    authors: 'Перышкин А.В.'\
>  },\
>  {\
>>    id: 'e0ae6d5a-c1c9-4c57-8b95-58e29751d168А'\
>>    title: 'Мастер и Маргарита.',\
>>    description: 'Классичечкий роман.',\
>>    authors: 'Булгаков М.А.'\
>  }\
])

* запрос для *поиска* полей документов коллекции **books** по полю *title*:\
const cursor = db.collection('books').find({ title: 'Сборник задач по физике.' })\

* запрос для *редактирования* полей: *description* и *authors* коллекции **books** по *_id* записи\
await db.collection('books').updateOne(\
>  { id: 'dce5ccf7-f598-4843-9284-8f9a8dd17903А' },\
>  {$set: { description': 'Сборник задач по физике новое издание.', authors: 'Петерсон М.И.' }}\
)
