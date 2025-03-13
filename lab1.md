## Лабораторная работа 1
### Титов Ярослав 
### ИУ8-12

### Задания:

    1.Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.
    2.Разархивируйте скаченный файл в директорию ~/boost_1_69_0
    3.Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
    4.Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
    5.Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
    6.Найдите полный пусть до файла any.hpp внутри библиотеки boost.
    7.Выведите в консоль все файлы, где упоминается последовательность boost::asio.
    8.Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.
    9.Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
    10.Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
    11.Найдите топ10 самых "тяжёлых".


## Команда 1
**команда:**

wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

**вывод:**

[ссыслка на файл](~/1.txt)

## Команда 2
**команда:**

tar -xzvf boost_1_69_0.tar.gz -C ~/boost_1_69_0

**вывод:**

[ссылка на файл](~/2.txt)

## Команда 3
**команда:**

ls -p boost_1_69_0 | grep -v / | wc -l

**вывод:**

12

## Команда 4
**команда**

find boost_1_69_0 -type f | wc -l

**вывод:**

61191

## Команда 5
**команда:**
- заголовочные файлы

  find boost_1_69_0 -type f \( -name "*.h" -o -name "*.hpp" \) | wc -l

- файлы с расширением .cpp

  find boost_1_69_0 -type f -name "*.cpp" | wc -l

- остальные файлы

  find boost_1_69_0 -type f \( ! -name "*.h" -a ! -name "*.hpp" -a ! -name "*.cpp" \) | wc -l

  **вывод:**
   - 15208
 
   - 13774
 
   - 32209
 
## Команда 6
**команда:**
  
find . -type f -name "any.hpp"

  **вывод:**

  ./boost_1_69_0/boost/any.hpp
./boost_1_69_0/boost/type_erasure/any.hpp
./boost_1_69_0/boost/hana/any.hpp
./boost_1_69_0/boost/hana/fwd/any.hpp
./boost_1_69_0/boost/fusion/include/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/any.hpp
./boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
./boost_1_69_0/boost/proto/detail/any.hpp
./boost_1_69_0/boost/xpressive/detail/utility/any.hpp
./boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp

## Команда 7
**команда:**

grep -r "boost::asio"

**вывод:**

[ссылка на файл](~/7.txt)

## Команда 8
**команда:**

компилирую boost по инструкции

## Команда 9
**команда:**

mkdir -p ~/boost-libs

cp  ~/boost_1_61_0/stage/lib/*.a ~/boost-libs/


## Команда 10
**команда:**

du -ah ~/boost-libs

**вывод:**

[ссылка на файл](~/10.txt)

## Команда 11
**команда:**

find ~/boost-libs -type f -exec du -ah {} + | sort -rh | head -n 10

**вывод:**

[ссылка на файл](~/11.txt)
  
