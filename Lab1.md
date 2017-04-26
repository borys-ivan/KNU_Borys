# Lab1

1.	Створити змінні базових (atomic) типів. Базові типи: character, numeric, integer, complex, logical.

a<-1L
b<-1
c<-'a'
d<-TRUE
e<-1 + 1i

2. Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14, 2.71, 0, 13; 100 значень TRUE.
•	Створити вектори, які: містить послідовність з 5 до 75
Для создания векторов, содержащих совокупность последовательных чисел, удобна функция seq() (от "sequence" – последовательность). Так, вектор с именем S, содержащий совокупность целых чисел от 1 до 7, можно создать следующим образом:
> S<-seq(5,75);
> S

 [1]  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29
[26] 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54
[51] 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75

•	містить числа 3.14, 2.71, 0, 13;

Вектор представляет собой поименованный одномерный объект, содержащий набор однотипных элементов (числовые, логические, либо текстовые значения - никакие сочетания  не допускаются). Для создания векторов небольшой длины в R используется т.н. функция конкатенации c() (от "concatenate" – объединять, связывать). В качестве аргументов этой функции через запятую перечисляют объединяемые в вектор значения, например:
> my.vector <- c(3.14,2.17,0.13);
> my.vector

[1] 3.14 2.17 0.13


100 значень TRUE.

> x<-1:100
> x

  [1]   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18
 [19]  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35  36
 [37]  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  53  54
 [55]  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72
 [73]  73  74  75  76  77  78  79  80  81  82  83  84  85  86  87  88  89  90
 [91]  91  92  93  94  95  96  97  98  99 100


> x<-replicate(100, c(TRUE))

  [1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [16] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [31] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [46] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [61] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [76] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
 [91] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE


3. Створити наступну матрицю за допомогою matrix, та за допомогою cbind або rbind
 
•	за допомогою matrix

> A=matrix(c(0.5,1.3,3.5,3.9,131,2.8,0,2.2,4.6,2,7,5.1),nrow=4,ncol=3,byrow=TRUE)
> A
     [,1]  [,2] [,3]
[1,]  0.5   1.3  3.5
[2,]  3.9 131.0  2.8
[3,]  0.0   2.2  4.6
[4,]  2.0   7.0  5.1


•	за допомогою cbind або rbind

> v1=c(0.5,3.9,0,2);
> v2=c(1.3,131,2.2,7);
> v3=c(3.5,2.8,4.6,5.1);
> cbind(v1,v2,v3);

      v1    v2  v3
[1,] 0.5   1.3 3.5
[2,] 3.9 131.0 2.8
[3,] 0.0   2.2 4.6
[4,] 2.0   7.0 5.1


4. Створити довільний список (list), в який включити всі базові типи.
>mylist<-list(a=c(1,2,3,4) ,b=c("a","b","c","d"),c=c(TRUE,FALSE,TRUE,FALSE));
> mylist

$a
[1] 1 2 3 4
$b
[1] "a" "b" "c" "d"
$c
[1]  TRUE FALSE  TRUE FALSE


5. Створити фактор з трьома рівнями «baby», «child», «adult».
> factor(levels= c("baby", "child", "adult"))

factor(0)
Levels: baby child adult


6. Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA,11. Знайти кількість значень NA.

•	Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA,11

> my.vector <- c(1,2,3,4,NA,6,7,NA,9,NA,11);
> my.vector
 [1]  1  2  3  4 NA  6  7 NA  9 NA 11
> my.vector[5]
[1] NA

match(NA, c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11))
[1] 5



•	Знайти кількість значень NA.

sum(is.na(c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)))
[1] 3



7. Створити довільний data frame та вивести в консоль.

> city <- c("City1", "City1", "City2", "City2", "City3", "City3")
> sex <- c("Male", "Female", "Male", "Female", "Male", "Female")
> number <- c(12450, 10345, 5670, 5800, 25129, 26000)
> CITY <- data.frame(City = city, Sex = sex, Number = number) 
> CITY

   City    Sex Number
1 City1   Male  12450
2 City1 Female  10345
3 City2   Male   5670
4 City2 Female   5800
5 City3   Male  25129
6 City3 Female  26000


8. Змінити імена стовпців цього data frame.

fix(CITY)

colnames(CITY)<-c('Test', 'City')

 



