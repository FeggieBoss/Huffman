# Домашнее задание №2 (`HW #2`)

Напишите программу, выполняющую сжатие двухпроходным алгоритмом Хаффмана.

1. **Ограничения.**
   * Наибольший размер входного файла — 5MB.
   * Ограничение на время выполнения — 5 секунд.

2. **Требования к реализации.**
   * Реализация должна быть выполнена в объектно-ориентированном стиле (например, включать классы `TreeNode`, `HuffTree`, `HuffmanArchiver`).
   * Для хранения элементов, там, где это уместно, должна быть использована библиотека STL (например, `std::vector`, а не динамический массив).
   * Ввод-вывод должен быть выполнен с помощью классов STL (`iostream`).
   * Должны использоваться исключения.
   * Должен быть реализован свой класс для автоматического тестирования или использована одна из библиотек (`google test`, `doctest`, etc).
   * Для методов должны быть написаны автотесты.
   * Действуют все стандартные требования.
3. **Параметры командной строки.** Значение параметра (если есть) указывается через пробел. Программа должна проверять корректность параметров и выводить сообщение об ошибке.
   * `-c`: архивирование
   * `-u`: разархивирование
   * `-f`, `--file <путь>`: имя входного файла
   * `-o`, `--output <путь>`: имя результирующего файла
4. **Вывод на экран.**
   Программа должна выводить на экран статистику сжатия/распаковки: размер исходных данных, размер полученных данных
   и размер, который был использован для хранения вспомогательных данных в выходном файле (например, таблицы).
   Не должно выводиться никакого дополнительного текста, только размеры. Все размеры в байтах.

   Например:
   ```
   $ ./huffman -c -f myfile.txt -o result.bin
   15678
   6172
   482
   ```

   Размер исходного файла (исходные данные): 15678 байт, размер сжатых данных (без дополнительной информации):
   6172 байта, размер дополнительных данных: 482 байта. Размер всего сжатого файла: 6172 + 482 = 6654 байта.
   ```
   $ ./huffman -u -f result.bin -o myfile_new.txt
   6172
   15678
   482
   ```
   Размер распакованного файла (полученные данные): 15678 байт, размер сжатых данных (без дополнительной информации):
   6172 байта, размер дополнительных данных: 482 байта. Размер всего исходного сжатого файла: 6172 + 482 = 6654 байта.