# RGR
МІНІСТЕРСТВО ОСВІТИ І НАУКИ УКРАЇНИ

Національний аерокосмічний університет ім. М. Є. Жуковського «Харківський авіаційний інститут»

Факультет «Радіоелектроніки, комп’ютерних систем та інфокомунікацій» Кафедра «Аерокосмічних радіоелектронних систем»

Розрахунково – графічна робота

з дисципліни «Інформаційно-комунікаційні мережі »

на тему: «Відображення тексту з git репозиторія у Jenkins»

Виконав: студент 4 курсу групи № 536-ст напряму підготовки (спеціальності) 172 «Телекомунікації та радіотехніка» Лазурко В.Є.

Прийняв: ас. каф. 501

Перетятько М. С.

Національна шкала:

Кількість балів:

Оцінка: ECTS

Харків 2021

Ціль роботи: Відобразити текст з git репозиторія у Jenkins.

ХІД РОБОТИ

Встановлюємо git на VM
![image](https://user-images.githubusercontent.com/79759252/117403248-8a538900-af10-11eb-9f80-093a577c82f8.png)
Далі заходимо в Jenkins в який ми вже заходили в 3 лабораторній.
Та встановлюємо плагин для Git
![image](https://user-images.githubusercontent.com/79759252/117403553-05b53a80-af11-11eb-8cb2-e8bdac40284d.png)
![image](https://user-images.githubusercontent.com/79759252/117403879-9855d980-af11-11eb-941e-4eb160ff1f06.png)
Якщо цього плагіну немає в Доступних то перевірте в вже Встановлених.
Тепер можемо створювати новий Item
Далее переходим снова в VM и генерируем ключи 1 для Jenkins 1 для github командой ssh-keygen

Получаем 2 ключа id_rsa id_rsa.pub

Чтобы их посмотреть нужно зайти в нужный репозиторий командой

cd .ssh а потом cat id_rsa и cat id_rsa.pub
![image](https://user-images.githubusercontent.com/79759252/117404448-a1937600-af12-11eb-8615-b1e26a6cb1ee.png)
![image](https://user-images.githubusercontent.com/79759252/117404572-d3a4d800-af12-11eb-84d9-47c24c6672f3.png)
![image](https://user-images.githubusercontent.com/79759252/117404645-f931e180-af12-11eb-8da5-e8cff0b7149f.png)
Створюємо SSH ключ в git та вставляємо туди id_rsa.pub
![image](https://user-images.githubusercontent.com/79759252/117405372-33e84980-af14-11eb-99ac-299a70e96575.png)
Тепер встановимо ключ в наш Item
![image](https://user-images.githubusercontent.com/79759252/117405647-9fcab200-af14-11eb-994d-809e7689e1b6.png)
Нажимаэмо Credentials > Add
і заповнюємо 
вибираємо в полі Kind
![image](https://user-images.githubusercontent.com/79759252/117405903-0223b280-af15-11eb-92e5-d641f168d179.png)
![image](https://user-images.githubusercontent.com/79759252/117406138-52027980-af15-11eb-86bd-c865be0701d9.png)
Нажимаємо Add та вибираэмо створений нами Credentials
Заходимо в github та обираэмо репозиторій
![image](https://user-images.githubusercontent.com/79759252/117406397-adcd0280-af15-11eb-9d0b-912b8f84234a.png)
Та вставляємо скопійованю команду в Jenkins
![image](https://user-images.githubusercontent.com/79759252/117406592-f2f13480-af15-11eb-842d-907ef6f91568.png)

Нажимаэмо зберегти и збираэмо наш проект
![image](https://user-images.githubusercontent.com/79759252/117408366-8297e280-af18-11eb-82eb-6f0ef25d232e.png)

Після цього бачимо що наш проект працює
![image](https://user-images.githubusercontent.com/79759252/117408511-ba9f2580-af18-11eb-9241-2047efc0965a.png)
Зелена галочка
Теперь ми можем посмотреть вивод в консоле
![image](https://user-images.githubusercontent.com/79759252/117408729-05b93880-af19-11eb-8210-e5891e9c0add.png)

![image](https://user-images.githubusercontent.com/79759252/117408801-1d90bc80-af19-11eb-9d9b-c81a475a6d36.png)
Ура! РГР закончена
Вивод: в цій РГР ми навчились використовувати Jenkins та зв'язали його з github. Створили ключи для того щоб Jenkins мав доступ до нашого git.
