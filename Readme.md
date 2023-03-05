# Что такое API
Api  (application programming interface)-

это контракт,который предоставляет программа.

"Ко мне можно обращаться так и так.я обязуюсь делать и то и это".

Это возможности,которые предоставляют разработчики языка для удобного взаимодействия с его функционалом.

* 1.Строки

* 2.Работа с файловой системой

* 3.Логирование

* 4.Импорт

* 5.Xml



## Строки

Создать строку из миллиона плюсиков

StringBuilder sb = new StringBuilder();

for(int i = 0; i < 1_000_000; i++){

    sb.append("+");

}

* concat() - объединение строк

* valueOf()- преобразует Object  в строковое представление

* join(): объединяет набор строк в одну с учетом разделителя

* charAt(): получение символа по индексу

* indexOf(): первый индекс вхождения подстроки

* lastIndexOf(): последний индекс вхождения подстроки

* startsWith()/endsWith(): определяет, начинается/заканчивается ли строка с подстроки

* replace(): замена одной подстроки на другую

* trim(): удаляет начальные и конечные пробелы

* substring(): возвращает подстроку, см.аргументы

* toLowerCase()/toUpperCase(): возвращает новую строку в нижнем/верхнем регистре

* сompareTo(): сравнивает две строки

* equals(): сравнивает строки с учетом регистра

* equalsIgnoreCase(): сравнивает строки без учета регистра

* regionMatches(): сравнивает подстроки в строках

# String vs StringBuilder

* Много изменений – String  // удобен для разбора существующего материала

* Много преобразований – StringBuilder // удобен для компиляции нового проекта

# Работа с файлаловой системой

* каталоги

* файлы

## Для работы нужно:
File <имя> = new File(<полный путь к файлу>);

File f1 = new File("file.txt");

File f2 = new File("/Users/sk/vscode/java_projects/file.txt");


import java.io.File;

public class fileSystemDemo {

 public static void main(String[] args) {

 String pathProject = System.getProperty("user.dir");

 String pathFile = pathProject.concat("/file.txt");

 File f3 = new File(pathFile);

 System.out.println(f3.getAbsolutePath ());

 // /Users/sk/vscode/java_projects/file.txt

 // C:/Users/Sk/Documents/xxx/brainexplosion/java/file.txt

    }

}

## Работа с файловой системой. Файлы. Ошибки


try {

 Код, в котором может появиться ошибка

} catch (Exception e) {

 Обработка, если ошибка случилась

}
finally {

 Код, который выполнится в любом случае

}

import java.io.File;

public class tryDemo {

 public static void main(String[] args) {

 try {

 String pathProject = System.getProperty("user.dir");

 String pathFile = pathProject.concat("/file.txt");

 File f3 = new File(pathFile);

 System.out.println("try");

 } catch (Exception e) {

 System.out.println("catch");

 }

 finally

 { System.out.println("finally"); }

 }

}

## Работа с файловой системой

* isHidden(): возвращает истину, если каталог или файл  является скрытым

* length(): возвращает размер файла в байтах

* lastModified(): возвращает время последнего изменения файла или каталога

* list(): возвращает массив файлов и подкаталогов, которые находятся в каталоге

* listFiles(): возвращает массив файлов и подкаталогов, которые находятся
в определенном каталоге

* mkdir(): создает новый каталог

* renameTo(File dest): переименовывает файл или каталог

# Логирование

Логи содержат системную информацию работы
программного или аппаратного комплекса.

В них записываются действия разного приоритета
от пользователя, или программного продукта.

Процесс ведения логов называют
“логированием” (журналированием).

## Логирование. Использование. Основы

Использование
Logger logger = Logger.getLogger()

Уровни важности
INFO, DEBUG, ERROR, WARNING и др.

Вывод
ConsoleHandler info = new ConsoleHandler();

log.addHandler(info);

Формат вывода: структурированный, абы как

XMLFormatter, SimpleFormatter