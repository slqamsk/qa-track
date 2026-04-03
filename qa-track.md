# Курсы по тестированию и обеспечению качества
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
    qa-base[Базовые IT-навыки для тестировщиков <br>24 а.ч.]
    tpo[Тестирование ПО. Уровень 1, 40 а.ч.]
    at-tpo[Основы тестирования ПО для автотестирования <br>16 а.ч.]
    qa-java[Java для автоматизированного тестирования <br>40 а.ч.]
    at-java1[Автоматизированное тестирования на Java. Уровень 1 <br>40 а.ч.]

    %% 2. ВСЕ СВЯЗИ (СТРЕЛКИ)
    qa-base --> tpo
    
    qa-base --> at-tpo
    qa-base --> qa-java

    tpo -.->|текст| at-java1
    at-tpo --> at-java1
    qa-java --> at-java1
````
