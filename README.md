<a name="logo"/>
<div align="center">
<a href="https://julialang.org/" target="_blank">
<img src="doc/src/assets/logo.svg" alt="Julia Logo" width="210" height="142"></img>
</a>
</div>

Documentation:
[![Documentation][docs-img]][docs-url]

[docs-img]: https://img.shields.io/badge/docs-v1-blue.svg "Documentation (version 1)"
[docs-url]: https://docs.julialang.org

Continuous integration:
[![Continuous integration (master)][buildkite-master-img]][buildkite-master-url]

<!--
To change the badge to point to a different pipeline, it is not sufficient to simply change the `?branch=` part.
You need to go to the Buildkite website and get the SVG URL for the correct pipeline.
-->
[buildkite-master-img]: https://badge.buildkite.com/f28e0d28b345f9fad5856ce6a8d64fffc7c70df8f4f2685cd8.svg?branch=master "Continuous integration (master)"
[buildkite-master-url]: https://buildkite.com/julialang/julia-master

Code coverage:
[![Code coverage (Coveralls)][coveralls-img]][coveralls-url]
[![Code coverage (Codecov)][codecov-img]][codecov-url]

[coveralls-img]: https://img.shields.io/coveralls/github/JuliaLang/julia/master.svg?label=coveralls "Code coverage (Coveralls)"
[coveralls-url]: https://coveralls.io/r/JuliaLang/julia?branch=master

[codecov-img]: https://img.shields.io/codecov/c/github/JuliaLang/julia/master.svg?label=codecov "Code coverage (Codecov)"
[codecov-url]: https://codecov.io/github/JuliaLang/julia?branch=master

## Язык Julia

Julia - это высокоуровневый, высокопроизводительный динамический язык для технических
расчётов. Главную домашнюю страницу Julia можно найти здесь -
[julialang.org](https://julialang.org/).  Это репозиторий GitHub
с руссифицированным исходным кодом Julia, включающая инструкции для компилирования
и установки Julia, приведённые ниже.

## Ресурсы

- **Домашняя странице:** <https://julialang.org>
- **Бинарники:** <https://julialang.org/downloads/>
- **Исходный код:** <https://github.com/JuliaLang/julia>
- **Документация:** <https://docs.julialang.org>
- **Пакеты:** <https://julialang.org/packages/>
- **Дискуссионный форум** <https://discourse.julialang.org>
- **Slack:** <https://julialang.slack.com> (get an invite from <https://julialang.org/slack/>)
- **YouTube:** <https://www.youtube.com/user/JuliaLanguage>
- **Code coverage:** <https://coveralls.io/r/JuliaLang/julia>

Новые разработчики могут найти заметки в файле
[CONTRIBUTING](https://github.com/JuliaLang/julia/blob/master/CONTRIBUTING.md) ,
которые помогут начать делать вклад в кодовую базу Julia.

### Внешние ресурсы

- [**StackOverflow**](https://stackoverflow.com/questions/tagged/julia-lang)
- [**Twitter**](https://twitter.com/JuliaLanguage)
- [**Образовательные ресурсы**](https://julialang.org/learning/)

## Бинарная Установка

Если у вас нет желания компилировать из исходников последнейшую версию Julia,
также [доступны для загрузки](https://julialang.org/downloads/) прекомпилированные
платформо-зависимые бинарные файлы. На странице загрузки также приведены детали
[по различным tiers of support](https://julialang.org/downloads/#support-tiers)
для комбинаций ОС и платформы.

если всё отлично работает, то вы увидете баннер Julia и
интерактивный промпт, в который можно вводить выражения для
обработки. Можно прочесть о том, [как начать](https://docs.julialang.org/en/v1/manual/getting-started/) в этом руководстве.

**Примечание**: Although some system package managers provide Julia, such
installations are neither maintained nor endorsed by the Julia
project. They may be outdated, broken and/or unmaintained. We
recommend you use the official Julia binaries instead.

## Построение Julia

Сначала убедитесь, что у вас есть и установлены все [необходимые
зависимости](https://github.com/JuliaLang/julia/blob/master/doc/src/devdocs/build/build.md#required-build-tools-and-external-libraries).
Затем обретите исходный код, клонировав данный репозиторий git:

    git clone https://github.com/JuliaLang/julia.git

По умолчанию вы будете строить последнейшую нестабильную версию
Julia. Однако для большинства пользователей подойдёт [самая свежая стабильная версия](https://github.com/JuliaLang/julia/releases)
интерпретатора Julia. Эту версию можно получить, перейдя в папку Julia
и выполнив:

    git checkout v1.7.0

Теперь запустите `make`, чтобы построить исполнимый файл `julia`.

Для построения Julia требуется 2GiB дискового пространства и приблизительно 4GiB виртуальной памяти.

**Примечание:** Процесс построения будет неудачен, если родительские папки папки построения
включают в свой путь пробелы или другие мета-символы оболочки, такие как `$` или `:` (это ограничения GNU make).

Как только построение окончено, можно выполнить исполнимый файл `julia`, если войти в папку с julia и написать 

    ./julia

Первый тест Julia определяет, насколько удачно построение.
Из командной строки UNIX/Windows внутри папки с исходниками `julia`,
наберите команду `make testall`. Вы должны увидеть вывод, перечисляющий
серию выполняемых тестов; если они завершаются без ошибок, то
можно приступать к использованию Julia.

Можно прочесть о  [начале
работы](https://docs.julialang.org/en/v1/manual/getting-started/)
в этом руководстве.

Детальный инструкции по построению, если необходимо,
включены в [документацию по построению](https://github.com/JuliaLang/julia/blob/master/doc/src/devdocs/build/).

### Удаление Julia

Julia не устанавливает ничего вне папки, в которую она клонирована.
Julia можно полностью удалить, удалив эту папку.
Пакеты Julia устанавливаются в `~/.julia` по умолчанию, их
можно удалить, удалив `~/.julia`.

## Организация Исходного Кода

Исмодный код Julia организован следующим образом:

| Папка         | Содержимое                                                                           |
| -                 | -                                                                                |
| `base/`           | исходный код модуля Base (часть стандартной библиотеки Julia)                    |
| `stdlib/`         | исходный код для других пакетов стандартной библиотеки                           |
| `cli/`            | исходник интерфейса командной строки interface/REPL                              |
| `contrib/`        | различные сценарии                                                               |
| `deps/`           | внешнии зависимости                                                              |
| `doc/src/`        | исходник руководства пользователя                                                |
| `src/`            | исходники ядра языка Julia                                                       |
| `test/`           | тестовые наборы                                                                  |
| `usr/`            | бинарники и динамические библиотеки, загружаемые стандартными библиотеками Julia |

## Терминал, Редакторы и IDE

Julia REPL довольно мошный. Смотрите раздел в руководстве на сайте
[Julia REPL](https://docs.julialang.org/en/v1/stdlib/REPL/) ,
чтобы узнатьподробности.

На Windows we highly recommend running Julia in a modern terminal,
such as [Windows Terminal from the Microsoft Store](https://aka.ms/terminal).

Support for editing Julia is available for many
[widely used editors](https://github.com/JuliaEditorSupport):
[Emacs](https://github.com/JuliaEditorSupport/julia-emacs),
[Vim](https://github.com/JuliaEditorSupport/julia-vim),
[Sublime Text](https://github.com/JuliaEditorSupport/Julia-sublime), and many
others.

For users who prefer IDEs, we recommend using VS Code with the
[julia-vscode](https://www.julia-vscode.org/) plugin.
For notebook users, [Jupyter](https://jupyter.org/) notebook support is available through the
[IJulia](https://github.com/JuliaLang/IJulia.jl) package, and
the [Pluto.jl](https://github.com/fonsp/Pluto.jl) package provides Pluto notebooks.
