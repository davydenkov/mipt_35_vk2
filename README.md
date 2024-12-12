# mipt_35_vk2

#Команда
Игорь Давыденков TeamLead
Яков Чибинин ML Engineer
Сторожев Илья ML Engineer

#Архитектура

Обучение с тюнингом оптуной. В работе улучшения качества (фича инжиринг, границы параметров) 

#Описание проекта (проектная задача):
Реклама ВКонтакте работает по тем же принципам, что и большинство рекламных систем, — на основе аукциона. Чем больше рекламодатель готов заплатить за показ рекламы пользователю, тем больше людей увидят его рекламу.

Важные условия работы аукциона:

Если ставка объявления cpm больше всех ставок всех остальных участников, то со 100%-ной вероятностью выигрывает объявление со ставкой cpm.
Если ставка объявления cpm равна максимальной ставке среди всех остальных участников, объявление со ставкой cpm выигрывает с вероятностью в 50%. В реальном аукционе объявление может выигрывать по совершенно другим правилам и вероятностям.
Система запоминает все объявления, которые видел пользователь в течение сессии, и не показывает их, даже если это самые дорогие объявления в аукционе.
Новая сессия начинается после отсутствия показов рекламы пользователю в течение 6 часов.
Ваша задача в рамках проекта — разработать модель, которая способна предсказывать количество людей, которые увидят конкретное рекламное объявление в будущем.

Для решения этой задачи используйте приложенный датасет.

Материалы для выполнения проекта:
Чтобы понять контекст задачи, мы рекомендуем изучить материалы VK Tech про работу рекламы и задачу по предсказанию охватов рекламных объявлений: https://vk.com/tech?w=wall-147415323_5400

Датасет: https://cloud.mail.ru/public/kdLW/T574PctKb

Описание:

Данные по пользователям: users.tsv.
Данные показов рекламы пользователям за два последовательных месяца: history.tsv.
Данные с объявлений для валидации алгоритма: validate.tsv.
Данные эталонных ответов алгоритма для валидационного датасета: validate_answers.tsv.
Все файлы в формате tsv (разделитель колонок – \t) с обязательным заголовком для всех колонок.

Описание файлов и колонок
Файл users.tsv:

user_id — уникальный идентификатор пользователя;
sex — указанный пользователем пол в анкете;
age — указанный пользователем в анкете возраст пользователя. 0 — не указан;
city_id — указанный пользователем в анкете город проживания. 0 — не указан.
Файл history.tsv:

hour — в какой час пользователь видел объявление;
cpm — цена показанного рекламного объявления в рекламном аукционе. Это значит, что на данном аукционе это была максимальная ставка;
publisher — площадка, на который пользователь увидел рекламу;
user_id — уникальный идентификатор пользователя.
Файл validate.tsv:

cpm — для какой цены объявления нужно сделать прогноз;
hour_start — предположительное время запуска рекламного объявления;
hour_end — предположительное время остановки рекламного объявления. По итогу прогноз делается для рекламного объявления, которое будет запущено в период времени [hour_start, hour_end];
publishers — на каких площадках объявление может быть показано;
audience_size — размер аудитории объявления, количество идентификаторов в поле user_ids;
user_ids — аудитория объявления — список пользователей, кому рекламодатель хочет показать объявление.
Файл validate_answers.tsv:

at_least_one — доля пользователей, которая увидит объявление хотя бы один раз;
at_least_two — доля пользователей, которая увидит объявление хотя бы два раза;
at_least_three — доля пользователей, которая увидит объявление хотя бы три раза.
