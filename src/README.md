# Счётчики: INSTRUCTION, LINE, BRANCH, COMPLEXITY


Выбрала счётчик BRANCH потому что на мой его использование охватывает все ветви условий и можно убедиться, что тестами покрыты все комбинации кода.

Более подробная информация о счётчиках представлена ниже на английском и на русском языках.


## English Version

**Instructions (C0 Coverage)**

The smallest unit JaCoCo counts are single Java byte code instructions. Instruction coverage provides information about the amount of code that has been executed or missed. This metric is completely independent from source formatting and always available, even in absence of debug information in the class files.

**Branches (C1 Coverage)**

JaCoCo also calculates branch coverage for all if and switch statements. This metric counts the total number of such branches in a method and determines the number of executed or missed branches. Branch coverage is always available, even in absence of debug information in the class files. Note that exception handling is not considered as branches in the context of this counter definition.

If the class files haven been compiled with debug information decision points can be mapped to source lines and highlighted accordingly:

No coverage: No branches in the line has been executed (red diamond)
Partial coverage: Only a part of the branches in the line have been executed (yellow diamond)
Full coverage: All branches in the line have been executed (green diamond)

**Cyclomatic Complexity**

JaCoCo also calculates cyclomatic complexity for each non-abstract method and summarizes complexity for classes, packages and groups. According to its definition by McCabe1996 cyclomatic complexity is the minimum number of paths that can, in (linear) combination, generate all possible paths through a method. Thus the complexity value can serve as an indication for the number of unit test cases to fully cover a certain piece of software. Complexity figures can always be calculated, even in absence of debug information in the class files.

The formal definition of the cyclomatic complexity v(G) is based on the representation of a method's control flow graph as a directed graph:

v(G) = E - N + 2

Where E is the number of edges and N the number of nodes. JaCoCo calculates cyclomatic complexity of a method with the following equivalent equation based on the number of branches (B) and the number of decision points (D):

v(G) = B - D + 1

Based on the coverage status of each branch JaCoCo also calculates covered and missed complexity for each method. Missed complexity again is an indication for the number of test cases missing to fully cover a module. Note that as JaCoCo does not consider exception handling as branches try/catch blocks will also not increase complexity.

**Lines**

For all class files that have been compiled with debug information, coverage information for individual lines can be calculated. A source line is considered executed when at least one instruction that is assigned to this line has been executed.

Due to the fact that a single line typically compiles to multiple byte code instructions the source code highlighting shows three different status for each line containing source code:

No coverage: No instruction in the line has been executed (red background)
Partial coverage: Only a part of the instruction in the line have been executed (yellow background)
Full coverage: All instructions in the line have been executed (green background)
Depending on source formatting a single line of a source code may refer to multiple methods or multiple classes. Therefore the line count of methods cannot be simply added to obtain the total number for the containing class. The same holds true for the lines of multiple classes within a single source file. JaCoCo calculates line coverage for classes and source file based on the actual source lines covered.
Выбираете один из счётчиков (на ваше усмотрение из первых трёх: INSTRUCTION, LINE, BRANCH)

## Русская версия

**Инструкции (покрытие C0)**

Наименьшая единица, которую считает JaCoCo, - это инструкции по байт-коду Java. Охват инструкций предоставляет информацию о количестве кода, который был выполнен или пропущен. Этот показатель полностью независим от исходного форматирования и всегда доступен даже при отсутствии отладочной информации в файлах классов.

**Филиалы (С1 Покрытие)**
JaCoCo также рассчитывает покрытие филиала для всех ifи switchоператоров. Эта метрика подсчитывает общее количество таких ветвей в методе и определяет количество выполненных или пропущенных ветвей. Покрытие веток всегда доступно, даже в отсутствие отладочной информации в файлах классов. Обратите внимание, что обработка исключений не рассматривается как ветви в контексте этого определения счетчика.

Если файлы классов были скомпилированы с отладочной информацией, точки принятия решения могут быть сопоставлены с исходными строками и выделены соответствующим образом:

Нет покрытия: не было выполнено ни одной ветки в строке (красный ромб)
Частичное покрытие: была выполнена только часть ветвей в линии (желтый ромб)
Полный охват: все ветки в линии были выполнены (зеленый бриллиант)

**Цикломатическая Сложность**

JaCoCo также вычисляет цикломатическую сложность для каждого неабстрактного метода и суммирует сложность для классов, пакетов и групп. Согласно его определению McCabe1996 цикломатическая сложность - это минимальное количество путей, которые в (линейной) комбинации могут генерировать все возможные пути с помощью метода. Таким образом, значение сложности может служить индикатором для количества случаев модульного тестирования, чтобы полностью охватить определенную часть программного обеспечения. Показатели сложности всегда можно рассчитать, даже при отсутствии отладочной информации в файлах классов.

Формальное определение цикломатической сложности v (G) основано на представлении графа потока управления метода в виде ориентированного графа:

v (G) = E - N + 2

Где E - количество ребер, а N - количество узлов. JaCoCo вычисляет цикломатическую сложность метода с помощью следующего эквивалентного уравнения на основе количества ветвей (B) и количества точек принятия решения (D):

V (G) = B - D + 1

На основе состояния покрытия каждой ветви JaCoCo также рассчитывает покрытую и пропущенную сложность для каждого метода. Опять пропущенная сложность является показателем количества пропущенных тестовых случаев, чтобы полностью охватить модуль. Обратите внимание, что, поскольку JaCoCo не учитывает обработку исключений, поскольку блоки try / catch ветвей также не увеличивают сложность.

**Линии**

Для всех файлов классов, которые были скомпилированы с отладочной информацией, можно рассчитать информацию покрытия для отдельных строк. Строка источника считается выполненной, когда выполнена хотя бы одна инструкция, назначенная этой строке.

В связи с тем, что одна строка обычно компилируется в инструкции из нескольких байт-кода, выделение исходного кода показывает три разных состояния для каждой строки, содержащей исходный код:

Нет покрытия: не было выполнено ни одной инструкции в строке (красный фон)
Частичное покрытие: только часть инструкции в строке была выполнена (желтый фон)
Полный охват: все инструкции в строке выполнены (зеленый фон)
В зависимости от форматирования исходного кода одна строка исходного кода может ссылаться на несколько методов или несколько классов. Поэтому счетчик строк методов не может быть просто добавлен, чтобы получить общее число для содержащего класса. То же самое относится и к строкам нескольких классов в одном исходном файле. JaCoCo рассчитывает покрытие строк для классов и исходного файла на основе фактических исходных строк.



