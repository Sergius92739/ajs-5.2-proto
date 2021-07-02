[![Build status](https://ci.appveyor.com/api/projects/status/7c4g8oy0jn72hlag/branch/master?svg=true)](https://ci.appveyor.com/project/Sergius92739/ajs-5-2-methods/branch/master)

# Домашнее задание к лекции «Классы, наследование»

**Важно**: каждая задача выполняется в виде отдельного проекта с собственным GitHub репозиторием.

**Важно**: код должен проходить ESLint без ошибок.

**Важно**: тесты должны обеспечивать 100% покрытие тестируемых функций по строкам.

**Важно**: решения должны быть построены на базе [шаблона Webpack](/ci-template).

В личном кабинете на сайте [netology.ru](http://netology.ru/) в поле комментария к домашней работе вставьте ссылки на ваш GitHub-проекты.

---

## Классы, наследование

### Легенда

Вы решили перейти на классы и реализовать иерархию, выделив в качестве базового класса класс `Character`, а для остальных персонажей создать классы, наследующиеся от него.

### Описание

Реализуйте описанную иерархию классов: класс `Character` является родительским для всех остальных, 6 дочерних классов `Bowerman`, `Swordsman`, `Magician`, `Daemon`, `Undead`, `Zombie` от него наследуются, сами задавая свои характеристики.

Свойства, которые должны быть у объектов класса `Character`:
1. `name` - имя
1. `type` - тип
1. `health` - уровень жизни
1. `level` - уровень персонажа
1. `attack` - атака
1. `defence` - защита

Конструктор класса должен соответствовать следующим требованиям:
1. `name` - строка, min - 2 символа, max - 10
1. `type` - один из типов (строка): Bowman, Swordsman, Magician, Daemon, Undead, Zombie

В случае, если передаются некорректные значения, должна выбрасываться ошибка (`throw new Error(...)`).

В вашей функции автоматически должны устанавливаться значения следующих полей:
1. health: 100
1. level: 1
1. Атака/защита:
    1. Bowman: 25/25
    1. Swordsman: 40/10
    1. Magician: 10/40
    1. Undead: 25/25
    1. Zombie: 40/10
    1. Daemon: 10/40

---

## Методы

### Легенда

Поскольку вы создавали классы для того, чтобы хранить в одном месте свойства объекта и его поведение, то пришла пора реализовать соответствующие методы.

#### Описание

Реализуйте в классе `Character` метод `levelUp`, который работает следующим образом:
1. На 1 повышает поле `level`;
1. На 20% повышает показатели `attack` и `defence`;
1. Приводит показатель `health` к значению 100.

Метод должен работать только если показатель жизни не равен 0. В противном случае генерируется ошибка (нельзя повысить левел умершего).

Реализуйте в класса `Character` метод `damage(points)`, который меняет внутреннее состояние объекта (`points` -  это урон, наносимый персонажу). Метод `damage(points)` ничего не возвращает и рассчитывает итоговое изменение жизни персонажа (`health`) по формуле: `health -= points * (1 - defence / 100)`, учитывая, что значение `health >= 0`.

Не забудьте написать unit-тесты, которые обеспечивают 100% покрытие функций и классов, которые вы тестируете.
