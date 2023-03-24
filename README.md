## Laboratory work I
Викторова Алина ИУ8-21
Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [+] 1. Ознакомилась со ссылками учебного материала
- [+] 2. Выполнила инструкцию учебного материала
- [+] 3. Составила отчет 

## Tutorial

1) Скачиваем библиотеку boost с помощью утилиты wget
```
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
![lb1](https://user-images.githubusercontent.com/126507425/227588149-857f3aff-2c39-4c6c-87ac-a0c7e4fe2a3e.png)

```
2)Разархивируем скаченный файл в директорию ~/boost_1_69_0
$ tar -xvf boost_1_69_0.tar.gz
```
```
3) Подсчитываем количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
$ ls -l | grep "^-" | wc -l
```
![изображение](https://user-images.githubusercontent.com/126507425/227594388-f8aa2eb3-8a1f-4243-a85f-9fe45a032bcf.png)
```
4) Подсчитываем количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
$ ls -l -R | wc -l
```
![изображение](https://user-images.githubusercontent.com/126507425/227595024-68cd165d-b1be-42b7-8581-c1683320e645.png)
```
5) Подсчитаем количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
$ ls -l -R | grep -c *.hpp
$ ls -l -R | grep -c *.cpp
$ ls -l -R | grep -v *.hpp | grep -v *.cpp | grep -v 'итого' | wc -l
```
![изображение](https://user-images.githubusercontent.com/126507425/227598561-614dff61-6418-42be-b09f-bc5e3357425b.png)
```
6) Найдём полный пусть до файла any.hpp внутри библиотеки boost.
$ find $PWD -type f -name any.hpp
```
![изображение](https://user-images.githubusercontent.com/126507425/227600060-8dd76621-c0b7-4b19-9eb3-1f9db9589a32.png)
```
7) Выведем в консоль все файлы, где упоминается последовательность boost::asio.
$ grep -R -l "boost::asio"
```
![изображение](https://user-images.githubusercontent.com/126507425/227601381-c9226b37-44c6-4489-be53-54ece534dd1e.png)
```
8) Скомпилируем boost
$ sudo apt install libicu-dev
$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install
```
![изображение](https://user-images.githubusercontent.com/126507425/227610726-231f90b1-a277-4895-ab66-48b81166682b.png)

```
9) Перенесём все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
$ mv ~/boost_1_69_0/boost_output/lib/ ~/boost-libs/
```
![изображение](https://user-images.githubusercontent.com/126507425/227611945-f68cdccd-766d-4d94-b226-31e00c3c48c3.png)

```
10) Подсчитаем сколько занимает дискового пространства каждый файл в этой директории.
$ du -h -a | sort -h
```
![изображение](https://user-images.githubusercontent.com/126507425/227613253-ab21e196-8dab-4b52-87c2-7a008449871c.png)

```
11) Найдём топ 10 самых "тяжёлых".
$ du -h -a | sort -r -h | head -n 10
```
![изображение](https://user-images.githubusercontent.com/126507425/227613478-ceff1903-eeef-431b-a9a1-b7c314d4a34b.png)
