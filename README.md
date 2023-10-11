# Трекер задач    
Описание    
Таск-менеджер для управления задачами и их сроками. API написан на базе встроенного HttpServer. 
    
Написаны несколько реализаций интерфейса Managers - хранение в памяти, хранение в файле и хранение в симулируемой БД.
    
Финальная версия хранения в БД состоит из слоев:    

· API между frontend и backend - HttpTaskServer (фильтрует поступающие запросы и запускает соответствующие процедуры на backend).
· Backend - HttpTaskManager (содержит всю логику, после рестарта backend должен восстанавливать данные из СУБД через load()).
· API между backend и СУБД - KVTaskClient (преобразует запрос с backend в корректный для нашей СУБД).
· СУБД - KVServer (симулирует БД).    

Стек:   
· Java 11 (Core, Collections)
· Junit5  
    
Функционал приложения:      
· хранение задач, эпиков и подзадач (подзадача не может существовать без эпика)
· создание, обновление и удаление задач, эпиков и подзадач    
· вывод задач, эпиков или подзадач    
· вывод списка подзадач определенного эпика   
· управление статусами задач и подзадач (эпик рассчитывается на основе его подзадач)  
· хранение и вывод списка последних просмотренных задач, эпиков и подзадач (без повторов и разделения по классам)
· хранение длительности, времени начала и окончания задач и подзадач (эпик рассчитывается на основе его подзадач)
· вывод списка задач и подзадач отсортированных в порядке приоритета времени начала   
· сохранение состояния списков задач, эпиков, подзадач и истории просмотров в БД  
· восстановление состояния списков задач, эпиков, подзадач и истории просмотров из БД 

Цели проекта    
В этом проекте отрабатывалось практическое применение:  
    
принципов ООП   
· утилитарных классов
· enum    
· классов времени
· структр данных  
· оценки асимптотической сложности    
· сериализации/десериализации объектов через gson
· обработки исключений    
· создания API на базе встроенного в java HttpServer  
· http-запросов и ответов
· JUnit тестирования  