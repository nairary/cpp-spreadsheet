# cpp-spreadsheet
 Электронная таблица (упрощённый аналог Microsoft Excel или Google Sheets) В ячейках таблицы могут быть текст или формулы. Формулы, как и в существующих решениях, могут содержать индексы ячеек.
 # Как установить?
 Вам понадобится cmake версии 3.8 или выше (https://cmake.org/) ANTLR версии 4.ХХ (https://www.antlr.org)
Установка:
+ mkdir ./build
+ cmake ../spreadsheet -DCMAKE_BUILD_TYPE=Release
+ cmake --build ./ If you need Debug version, use -DCMAKE_BUILD_TYPE=Debug flag
# Руководство по применению
```
auto sheet = CreateSheet();           Создали новую таблицу
sheet->SetCell("A2"_pos, "meow");   |
sheet->SetCell("B2"_pos, "=1+2");   | Добавили формулы в ячейки
sheet->SetCell("A1"_pos, "=1/0");   |

std::ostringstream texts;
sheet->PrintTexts(texts);             Вывели ячейку с текстом в поток вывода ***std::ostringstream***
std::string str = texts.str();

std::ostringstream values;
sheet->PrintValues(values);           Вывели значения ячеек таблици в поток вывода ***std::ostringstream***

sheet->ClearCell("B2"_pos);           Удалили ячейку ***B2*** область вывода изменена
```
# TODO
Развитие в сторону добавления графического интерфейса
