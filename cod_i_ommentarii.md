### Console.WriteLine("Введите элементы массива через пробел:");
### string input = Console.ReadLine();
### string[] inputArray = input.Split(new[] { ' ' },StringSplitOptions.RemoveEmptyEntries);
-Split - разделение. В качестве разделителя используется пробел.
StringSplitOptions.RemoveEmptyEntries - удаление пустот.
Если, например, пробел случайно был нажат более одного раза, или пробел был нажат после введения последнего элемента.

#### 1. Подсчет количества элементов, длина которых менее либо равна трем символам.

### int count = 0; 
-переменная для подсчета кол-ва выполненных условий (количество строк, длина которых меньше, либо равна 3 символам)
### for (int i = 0; i < inputArray.Length; i++)
### {
### if (inputArray[i].Length <= 3) // проверяем длину каждой строки (элемента) в массиве, который мы ввели.
### {
### count++; 
### }
### }

### string[] resultArray = new string[count]; 
-в зависимости от count в новом массиве будет count строк (элементов).
Например, ввели n строк, из них 3  - подходят под условия, значит, у нас будет новый массив с тремя элементами.


#### 2. Заполнение нового массива элементами с символами, прошедших проверку.

### int index = 0;
-счетчик, индекс нового массива. 
### for (int i = 0; i < inputArray.Length; i++)
### {
### if (inputArray[i].Length <= 3)
### {
### resultArray[index] = inputArray[i];
### index++;
### }
### }

### string inputOutput = string.Join("\", \"", inputArray);
### string resultOutput = string.Join("\", \"", resultArray); 
-переменные inputOutput и  resultOutput объявлены для удобства форматированного вывода массивов в виде, который приведен в примере.

### Console.WriteLine($"[\"{inputOutput}\"] -> [\"{resultOutput}\"]");