**Решение 1**

Создадим манифесты всех необходимых нам ресурсов

[backet-s3.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/backet-s3.tf)

[inst_group.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/inst_group.tf)

[nlb.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/nlb.tf)

[providers.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/providers.tf)

[variables.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/variables.tf)

[vpc_lamp.tf](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/vpc_lamp.tf)


Сделаем terraform apply

![Image alt](https://github.com/mezhibo/devops2302/blob/587e27968938a32057fccf285263343983301ea2/IMG/1.jpg)


Зайдем, посмотрим что бакет создался с нашей картинкой


![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/2.jpg)


Откроем картинку по ссылке в нашем бакете


![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/3.jpg)



Видим что создалась Instance Group с тремя ВМ и шаблоном LAMP


![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/4.jpg)


Затем проверим создание и настройку сетевого балансировщика и привязку к нему инстанс группу с веб серверами

![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/5.jpg)


Скопируем ip-адрес нашего балансировщика и вставим его в браузер, должна будет открыться наша страница согласно описанию юзер даты при создании вм

```
    user-data  = <<EOF
#!/bin/bash
cd /var/www/html
echo '<html><head><title>Tree</title></head> <body><h1>Hello!</h1><img src="http://mezhibo-netology-s3.website.yandexcloud.net/tree"/></body></html>' > index.html
EOF
    }
```

![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/6.jpg)

Как видим веб-страница отображается корректно


Теперь оставим 2 из 3 виртуальных машин, и проверим что у нас все равно сайт работает, и балансировщик перенаправляет траффик на один оставшйися сервер

Выключаем машины 


![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/7.jpg)


Но сайт по прежнему доступен

![Image alt](https://github.com/mezhibo/devops2302/blob/d9790092596298c27126072c0691908d550d0843/IMG/8.jpg)
