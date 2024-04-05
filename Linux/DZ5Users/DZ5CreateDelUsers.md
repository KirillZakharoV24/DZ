# Создание пользователей
1. Создаём пользователей и директорию для них с помощью команды sudo useradd -m "имя пользователя"
2. Создаём группы при помощи команды sudo groupadd
3. Назначаем вторичные и первичные группы sudo usermod -g или -G
4. Назначаем пароли для пользователей sudo passwd "UserName"
Проверяем создание пользователей, принадлежность к группам и пароли чтением файлов group, passwd, shadow при помощи команды sudo cat etc/

Результат создания пользователей

![Group](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/group.png)

![Passwd](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/passwd.png)

![Shadow](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/shadow.png)

# Создание пользователя вручную путём редактирования файлов (nano)

#### 1. Чтобы вручную добавить нового пользователя в систему в
файл /etc/passwd, добавьте следующую строку:
testuser:x:3000:3000:test user:/home/testuser:/bin/bash
Добавлен пользователь «testuser» с идентификатором 3000.

Пользователь добавлен в группу с таким же идентифика-
тором, которая еще не создана. У пользователя установлен

комментарий, гласящий «test user», домашний каталог
установлен как "/home/testuser", а командная оболочка
– как "/bin/bash". Cохраните файл.

![Passwd](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/CreateNewUserPasswd.png)

#### 2. Необходимо добавить запись в /etc/shadow для этого пользователя. 

Скопируйте строку какого-нибудь существующего

пользователя, например
drobbins: $1$1234567890123456789012345678901:11664:0:-
1:-1:-1:-1:0
Замените имя пользователя в скопированной строке на имя
вашего пользователя и убедитесь что все поля (особенно
старый пароль) установлены:
testuser: $1$1234567890123456789012345678901:11664:0:-1:-
1:-1:-1:0
Сохраните внесенные изменения.

![Shadow](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/CreateNewUserShadow.png)

#### 3. Теперь необходимо определить пароль для нового пользователя. 
Введите в командной строке команду
passwd testuser и определите пароль пользователя.

#### 4. Если решено добавить созданного пользователя к уже имеющейся группе, то не понадобиться создавать новую группу в /etc/groups. Если это не так, то необходимо добавить новую группу для этого пользователя, введя в файл следующую строку:
testuser:x:3000:

![Group](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/CreateNewUserGroup.png)

#### 5. Создание домашнего каталога нового пользователя.

Для создания домашнего каталога нового пользователя выполните следующие команды:

cd /home

mkdir testuser

chown testuser:testuser testuser

chmod o-rwx testuser

Результаты добавления пользователя:

![AllUsersPasswd](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/AllUsersPasswd.png)

![AllUsersGroup](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/AllUSersGroup.png)

![AllUsersShadow](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/AllUsersShadow.png)

# Удаление пользователя с директорией

Удаляем пользователя вместе с его директорией при помощи команды: 

sudo userdel -r "UserName"

![DelPetrov](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/DeletePetrov.png)

# Файлы /etc/profile и $HOME/.profile.

Информация файла профиля /etc/profile используется при
входе в систему каждого пользователя. Этот файл обычно
содержит:
- глобальные или локальные переменные среды;
- информацию о пути к файлам в переменной PATH;
- параметры терминала;
- меры безопасности;
- советы дня или сведения о причинах отказа.

После выполнения /etc/profile пользователь попадает в
свой домашний каталог $HOME. В этом каталоге хранится

вся личная информация пользователя. Если в $HOME имеет-
ся файл .profile, система использует его в качестве исходно-
го файла. Установки /etc/profile могут быть переопределены

при добавлении в файл .profile нового элемента с другим
значением либо при выполнении команды unset. Настройка
файла .profile остается в распоряжении пользователя.

Каталог /etc/skel/: каталог с файлами по умолчанию, которые копируются в домашний каталог каждого пользователя

# Расшифровка строк в файлах shadow, group, passwd, gshadow

![Passwd](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/Lines/LineEtcPasswd.png)

![Group](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/Lines/LineEtcGroup.png)

![Shadow](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/Lines/LineEtcShadow.png)

![Shadow2](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/Lines/shadowLine.png)

![Gshadow](https://github.com/KirillZakharoV24/DZ/blob/main/Linux/DZ5Users/Lines/LineEtcGshadow.png)
