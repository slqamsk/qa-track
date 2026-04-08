# Курсы по тестированию и обеспечению качества
## Существующая линейка курсов по тестированию
```mermaid
graph LR
    oprog-a[<span style="white-space: nowrap;">Основы программирования</span> и баз данных, 24 а.ч.]
    bkp2[Microsoft Excel. <br> Уровень 1, 16 а.ч.]

    dzhv1-a[Java-1, 40 а.ч.]
    java2[Java-2, 40 а.ч.]
    
    tpo[Тестирование ПО. Уровень 1, 40 а.ч.]
    tpo21[Тестирование ПО. Уровень 2. Тест-дизайн, 24 а.ч.]
    upkot[Тестирование ПО. Уровень 2. Управление командой тестирования, 16 а.ч.]

    avtest[Автоматизированное тестирование веб-приложений с использованием Selenium, 40 а.ч.]

    oprog-a --> tpo
    bkp2 --> tpo

    tpo --> tpo21
    tpo --> upkot

    tpo -.->|Не обязательно| avtest

    dzhv1-a --> java2 --> avtest
````

## Дополнительный курс по АТ
```mermaid
graph LR
    oprog-a[<span style="white-space: nowrap;">Основы программирования</span> и баз данных, 24 а.ч.]
    bkp2[Microsoft Excel. <br> Уровень 1, 16 а.ч.]

    dzhv1-a[Java-1, 40 а.ч.]
    java2[Java-2, 40 а.ч.]
    
    tpo[Тестирование ПО. Уровень 1, 40 а.ч.]
    tpo21[Тестирование ПО. Уровень 2. Тест-дизайн, 24 а.ч.]
    upkot[Тестирование ПО. Уровень 2. Управление командой тестирования, 16 а.ч.]

    avtest[Автоматизированное тестирование веб-приложений с использованием Selenium, 40 а.ч.]

    at-api-long[Автоматизированное тестирование API, 40 а.ч.]
    at-api-short[Автоматизированное тестирование API, 16 а.ч.]

    oprog-a --> tpo
    bkp2 --> tpo

    tpo --> tpo21
    tpo --> upkot

    tpo -.->|Не обязательно| avtest
    tpo -.->|Не обязательно| at-api-long

    dzhv1-a --> java2

    java2 --> avtest
    java2 --> at-api-long

    avtest --> at-api-short

````

## Линейка курсов для ручного тестирования
```mermaid
graph LR
    subgraph prep [Предварительная подготовка]
        upPrep( )
        subgraph prep2 [Второй вариант подготовки]
            qa-base[Базовые IT-навыки для тестировщиков, 24 а.ч.]
        end

        subgraph prep1 [Первый вариант подготовки]
            oprog-a[<span style="white-space: nowrap;">Основы программирования</span> и баз данных, 24 а.ч.]
            bkp2[Microsoft Excel. <br> Уровень 1, 16 а.ч.]
        end
        
        %% Невидимый узел в центре блока
        centerPrep( )
    end
    
    tpo[Тестирование ПО. Уровень 1, 40 а.ч.]
    tpo21[Тестирование ПО. Уровень 2. Тест-дизайн, 24 а.ч.]
    upkot[Тестирование ПО. Уровень 2. Управление командой тестирования, 16 а.ч.]

    %% Стрелка из невидимого узла
    centerPrep --> tpo
    
    %% Связываем невидимый узел с содержимым блока (невидимыми линиями)
    upPrep ~~~ centerPrep
    oprog-a ~~~ centerPrep
    bkp2 ~~~ centerPrep
    prep1 ~~~ centerPrep
    prep2 ~~~ centerPrep
    
    tpo --> tpo21
    tpo --> upkot
    
    %% Скрываем невидимый узел
    style upPrep fill:transparent,stroke:transparent
    style centerPrep fill:transparent,stroke:transparent

````

## Линейка курсов для автоматизированного тестирования
```mermaid

graph LR
    %% 1. ОБЪЯВЛЕНИЕ ВСЕХ УЗЛОВ
    subgraph prep-qa [Предварительная подготовка, QA]
        subgraph prep2 [Второй вариант подготовки]
            at-tpo[Основы тестирования ПО для автотестирования <br>, 16 а.ч.]
        end

        subgraph prep1 [Первый вариант подготовки]
            tpo[Тестирование ПО. Уровень 1, 40 а.ч.]
        end
        %% Невидимый узел в центре блока
        centerPrep-qa( )
    end

    subgraph prep-java [Предварительная подготовка, Java]
        subgraph prep-java-new [Первый вариант подготовки]
            qa-java[Java для автоматизированного тестирования <br>40 а.ч.]
        end
        subgraph prep-java-old [Второй вариант подготовки]
            direction LR
            dzhv1-a[Java-1, 40 а.ч.] --> java2[Java-2, 40 а.ч.]
        end
        %% Невидимый узел в центре блока
        centerPrep-java( )
    end
    
    avtest[Автоматизированное тестирование веб-приложений с использованием Selenium, 40 а.ч.]

    %% 2. ВСЕ СВЯЗИ (СТРЕЛКИ)

    prep1 ~~~ centerPrep-qa
    prep2 ~~~ centerPrep-qa
    prep-java-new ~~~ centerPrep-java
    prep-java-old ~~~ centerPrep-java


    centerPrep-qa --> avtest
    centerPrep-java --> avtest

    %% Скрываем невидимый узел
    style centerPrep-qa fill:transparent,stroke:transparent
    style centerPrep-java fill:transparent,stroke:transparent
````
