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


![Image alt](скрин2)


Откроем картинку по ссылке в нашем бакете


![Image alt](скрин3)



Видим что создалась Instance Group с тремя ВМ и шаблоном LAMP


![Image alt](скрин4)


Затем проверим создание и настройку сетевого балансировщика и привязку к нему инстанс группу с веб серверами

![Image alt](скрин5)



