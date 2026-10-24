# WuppieFuzz: фаззинг REST API с учётом состояния, управляемый покрытием

**Оригинальное название:** *WuppieFuzz: Coverage-Guided, Stateful REST API Fuzzing*

| Поле               | Значение                                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------------------------- |
| Авторы             | Thomas Rooijakkers, Anne Nijsten, Cristian Daniele, Erieke Weitenberg, Ringo Groenewegen, Arthur Melissen   |
| Аффилиации         | TNO (Нидерланды); Radboud University (Нидерланды)                                                           |
| Публикация         | Препринт arXiv:2512.15554v1 [cs.SE], 17.12.2025; 12 страниц. Версия в трудах ICISSP 2026: том 2, с. 221–231 |
| DOI                | [10.48550/arXiv.2512.15554](https://doi.org/10.48550/arXiv.2512.15554) (препринт)                           |
| Лицензия оригинала | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode.ru) (препринт arXiv)                                  |
| Язык оригинала     | английский                                                                                                  |
| Переводчик         | А. Н. Сенников                                                                                              |

## Материалы

- [Перевод](wuppiefuzz-ru.md) — с примечаниями переводчика (сноски 3–6).
- [Оригинал](https://arxiv.org/abs/2512.15554v1).
- [Версия в трудах ICISSP 2026](https://doi.org/10.5220/0014327000004061) — с. 221–231; лицензия [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/legalcode.ru), для перевода не использовалась.
- [Код WuppieFuzz](https://github.com/TNO-S3/WuppieFuzz) — Apache 2.0.
- [Petstore](https://github.com/swagger-api/swagger-petstore) — тестовый API.

## Что сделано в работе

- Представлен WuppieFuzz — опенсорс-фаззер REST API на LibAFL, поддерживающий белый, серый и чёрный ящик. По спецификации OpenAPI он строит начальный корпус последовательностей запросов, мутирует их REST-специфичными мутаторами и мутаторами из LibAFL и направляет поиск по измеренному покрытию.
- Фаззер автоматизирует создание обвязки и формирует отчёты: граф зависимостей API, начальный корпус, покрытие эндпоинтов и кода, панель мониторинга. Реализация написана на Rust и опубликована под Apache 2.0.
- Оценка проведена на API Petstore: шесть планировщиков LibAFL, сравнение белого и чёрного ящика по десять прогонов, покрытие эндпоинтов и кода во времени. Покрытие эндпоинтов составило 17/58–20/58 в обоих режимах: белый ящик немного быстрее выходит на плато, но итоговое покрытие не увеличивает.
- В белом ящике начальное покрытие строк составляет около 25%, за первые минуты оно достигает около 27% и затем не растёт более двух часов. Фаззер быстро исследует большинство путей, но затем ему трудно находить новые интересные запросы.

## Правовое основание

Оригинал перевода — препринт arXiv:2512.15554v1, распространяемый по лицензии CC BY 4.0. Версия в трудах ICISSP 2026 опубликована под CC BY-NC-ND 4.0 и для перевода не использовалась. Лицензия CC BY 4.0 разрешает перевод, распространение и адаптацию с указанием авторов, названия и источника, со ссылкой на лицензию и с отметкой об изменениях. Перевод неофициальный, не связан с авторами оригинала и SciTePress. См. [ATTRIBUTION.md](../../ATTRIBUTION.md).

## Как цитировать оригинал

Версия в трудах: Rooijakkers, T.; Nijsten, A.; Daniele, C.; Weitenberg, E.; Groenewegen, R.; Melissen, A. WuppieFuzz: Coverage-Guided, Stateful REST API Fuzzing. In *Proceedings of the 12th International Conference on Information Systems Security and Privacy (ICISSP 2026)*, Vol. 2; SciTePress, 2026; pp. 221–231. https://doi.org/10.5220/0014327000004061

Препринт: Rooijakkers, T.; Nijsten, A.; Daniele, C.; Weitenberg, E.; Groenewegen, R.; Melissen, A. WuppieFuzz: Coverage-Guided, Stateful REST API Fuzzing. arXiv:2512.15554v1 [cs.SE], 2025. https://doi.org/10.48550/arXiv.2512.15554
