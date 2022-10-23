Лабораторная работа номер 2
Part 1.

mkdir workspace/lab02 //создаем директорию с этой лабой

cd workspace/lab02 //создаем директорию с этой лабой

git init //создаем локальный репозиторий

git remote add lab0.2 https://github.com/ideomat75/lab02.git //устанавливаеv подключение к удаленному серверу и git репозиторию на нем
 
touch README.md    //создаем файл

git add README.md  // добавляем его в локальный репозиторий
 
git commit -m"added README.md"  //оставляем коммит

git push --force lab0.2 master //пушим его в удаленный репозиторий на ветку master

![image]![image](https://user-images.githubusercontent.com/90716549/157384963-8d3b6781-a889-47e3-a6eb-3b891db275b3.png)

![image](https://user-images.githubusercontent.com/90716549/157385180-69f9c6d6-5afe-4426-81ef-6703f3379e32.png)

 touch hellooo_world.cpp  //создаем файл
 
 cat > hellooo_world.cpp << EOF //прочитаем ввод и перенаправим его вместо вывода на экран в файл
 
 #include <iostream>
 
 using namespace std;
 
 int main()
 
 {
 
 cout <<""Hello world!"<< endl;
 
 }
 
 EOF
 
 ![image](https://user-images.githubusercontent.com/90716549/157385913-36926d63-64be-4f87-a214-b5f4f2fa7e5a.png)
 
 git add hellooo_world.cpp //добавляет файл в локальную копию репозитория
 
 git commit -m"added file.cpp" //коммитим изменения с *осмысленным* сообщением.
 
 nano hellooo_world.cpp //изменяем код
 
 git commit -m" updated file.cpp" -a // -a позволяет не добавлять файл повторно
 
 git push --force lab0.2 master 
 
 ![image](https://user-images.githubusercontent.com/90716549/157386490-810921fd-a0dd-456c-93ac-3eafb4731ffa.png)
 
 
 Part 2
 
 git сheckout -b patch1  //создаем новую ветку и переходим на нее
 
 nano hellooo_world.cpp //изменяем код
 
 git commit -m"updated file.cpp" -a

 git push --force lab0.2 patch1
 
 ![image](https://user-images.githubusercontent.com/90716549/157387186-6705a784-8d0c-412f-a0b0-1020d6aef7cb.png)

  nano hellooo_world.cpp 
 
 git commit -m"updated file.cppX2" -a
 
 git push lab0.2 patch1 //все по старому
 
 git checkout master //перемещаемся на ветку master
 
 git merge patch1  //мержим ее и patch1
 
 git push --force lab0.2 master //заливаем изменения в удаленный репозиторий
 
  git push lab0.2 --delete patch1  //удаляем patch1 в удаленном репозитории
 
 ![image](https://user-images.githubusercontent.com/90716549/157387780-9128b23e-6b27-45fa-b605-562bfbef9957.png)
 
 
 ![image](https://user-images.githubusercontent.com/90716549/157387890-14201ccc-3d40-4db0-930d-9a0dcb691f2e.png)

git pull lab0.2 master //загружаем файл в локальный репозиторий
 
git log //смотрим историю коммитов
 
 git branch -d patch1 //удаляем ветку в локальном репозитории
 
 ![image](https://user-images.githubusercontent.com/90716549/157388350-a6774e0e-3446-4256-b9d0-d241e0d8cf90.png)
 
 ![image](https://user-images.githubusercontent.com/90716549/157388549-d8f3c615-ecc2-4aac-b649-6df64987dc4c.png)

 //тут начало Part3
 
 
 Part 3
 
 git checkout -b patch2
 
 sudo apt install clang-format
 
 lang-format -i -style=Mozilla hello_world.cpp
 
 git commit -m"new style" -a
 
 git push --force lab0.2 patch2

 ![image](https://user-images.githubusercontent.com/90716549/157389191-3e3e62c2-5f91-4832-b78b-df5fadc9f8cf.png)

 git checkout master 
 
 git pull lab0.2 master
 
  git checkout patch2
 
 git rebase master //пытаемся объединить изменения, сделанные в одной ветке, с другой веткой - видим конфликты
 
  nano hellooo_world.cpp //устраняем конфликты вручную 
 
 git add hellooo_world.cpp
 
 rebase --continue //объединяем изменения, сделанные в одной ветке, с другой веткой
 
 ![image](https://user-images.githubusercontent.com/90716549/157389388-87973539-2ce8-43cf-852b-db1357fb0fce.png)
 
 git push --force lab0.2 patch2 //пушим изменения в удаленный репозиторий
 
 git checkout master
 
 git merge patch2
 
 ![image](https://user-images.githubusercontent.com/90716549/157389546-eecf3041-7a3e-42d5-ae69-78347f699837.png)

 
 
 ![image](https://user-images.githubusercontent.com/90716549/157389647-f74fe564-7c46-472e-bb38-10bea288d16b.png)

 
 ![image](https://user-images.githubusercontent.com/90716549/157389726-d70649a2-cbdf-4e97-8845-32afe9c97387.png)



 
 
