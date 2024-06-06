# Задание №7. Оптимизация `test-suite` и сбор `DX`-метрик

В этом задании вам нужо попрактиковаться в оптимизации `test-suite` и сборе `DX`-метрик.

## Оптимизация test-suite
Можно оптимизировать test-suite `dev.to`, либо своего проекта.

В любом случае для сдачи задания нужно написать `case-study` о сделанной оптимизации.

Вооружитесь инструментами, рассмотренными на лекции, и разгоните этот test-suite!

## Сбор DX-метрики

Чтобы запечатлеть свой прогресс и в дальнейшем защитить его от деградации, сделайте сбор `DX`-метрики времени выполнения `test-suite` в `InfluxDB` и постройте график в `Chronograf`.

Сделать это очень просто с помощью https://github.com/influxdata/sandbox и https://github.com/palkan/influxer.

Подумайте, как бы вам было удобно прикрепить отправку метрики в `InfluxDB` к прогону тестов.

## Hints

Старайтесь держать `feedback-loop` коротким. `test-suite` `dev.to` целиком в один процесс выполняется около 10 минут, это очень долго.

Используйте семплирование или работайте с конкретными наиболее долгими тестами.

Если вы обнаружите проблему, то выберите какой-нибудь один тест, на котором она воспроизводится, и исправьте её, работая с этим тестом.

Попробуйте все инструменты из `test-prof`!

`json-flamegraph` для всего `test-suite` целиком занимает около `1Gb`. `Speedscope.app` открыть его не может.

C отчётом `stackprof` для всего `test-suite` можно работать через `CLI stackprof`, и через `qcachegrind`.

С `ruby-prof` надо работать ещё аккуратнее, потому что он, как `tracing profiler`, собирает очень много данных, с которыми в дальнейшем тяжело работать.


## Чек-лист для сдачи задания
- [ ] PR в этот репозиторий с `case-study` о проделанной оптимизации и достигнутых результатах в описании
- [ ] Если оптимизируете `dev.to`, то сделать `PR` с оптимизацией и case-study в https://github.com/hardcode-dev/rails-optimization-task6 и прислать ссылку на него
- [ ] Добавить скриншот с графиком изменения времени прогона `test-suite` в `Chronograf` по мере оптимизации
