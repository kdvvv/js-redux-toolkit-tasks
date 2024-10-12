# Механизм ExtraReducers

В этом задании мы продолжим добавлять новые функции в наше приложение, имитирующее форум.

Удаление любой сущности влечет за собой побочные эффекты. Например, в нашем приложении есть авторы. Если автора удалить, то все его посты и комментарии останутся без привязки к пользователю.

В реальных приложениях обычно удаления из базы данных не происходит. Сущность просто помечается как удаленная, поэтому связи не теряются. Мы же для практики будем удалять все привязанные данные, для этого можно использовать _Extra Reducers_.

Реализуйте удаление привязанных сущностей:

- При удалении пользователя должен удаляться весь контент его авторства.
- При удалении постов должны удаляться все комментарии, привязанные к этому посту.

Для удобства тестирования на форму выведены таблицы со всем контентом, сгруппированные по пользователям.

## src/slices/commentsSlice.js

Реализуйте необходимые дополнительные редьюсеры, которые будут удалять комментарии при удалении пользователя или поста.

## src/slices/postsSlice.js

Добавьте дополнительный редьюсер, который будет удалять посты при удалении пользователя.

## Подсказки

- Для обновления коллекции подойдет метод [setAll()](https://redux-toolkit.js.org/api/createEntityAdapter#crud-functions).
- При удалении поста в действие передается объект с постом, а не только его `id`. Это упрощает работу в дополнительных редьюсерах — например, удаление комментариев этого же поста.