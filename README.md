<h3>Review Service</h3>
<h4>Предоставляет REST API для работы с пользовательскими отзывами к блюдам, а также для расчета рейтинга блюда и его средней оценки<br>
Информация о зарегистрированном пользователе передается в токене доступа.</h4>
<ul class="mt-2">
    <li class="mt-2"><i>POST /v1/reviews</i> - создать отзыв, рейтинг блюда должен быть от 1 до 5. Доступно зарегистрированным пользователям</li>
    <li class="mt-2"><i>GET /v1/reviews/{id}</i> - получить отзыв по ID. Доступно всем пользователям</li>
    <li class="mt-2"><i>GET /v1/reviews/my?sort={sort}&from={from}&size={size}</i> - получить пагинированный список (offset paging) отзывов конкретного пользователя. 
    Список отсортирован по дате создания (DATE_ASC, DATE_DESC).  Доступно зарегистрированным пользователям</li>
    <li class="mt-2"><i>GET /v1/reviews/menu-items/{menuId}?sort={sort}&from={from}&size={size}</i> - получить пагинированный список отзывов к конкретному блюду. 
    Список отсортирован по дате создания (DATE_ASC, DATE_DESC). В ответе также передается информация о рейтинге и средней оценке блюда. Доступно всем пользователям</li>
    <li class="mt-2"><i>POST /v1/reviews/ratings</i> - получить рейтинги и средние оценки блюд, идентификаторы которых передаются в теле запроса. Рейтинг блюда рассчитывается согласно доверительному интервалу биномиального распределения по методу Уилсона (Wilson Score Confidence Interval).
     Доступно всем пользователям</li>
</ul>   
Данные хранятся в реляционной базе PostgreSQL 16.
