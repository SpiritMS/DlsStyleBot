# DlsStyleBot

## Описание проекта
Это код Telegram бота, который реализует быстрый перенос Вашего стиля с картины на Вашу фотографию.

Это происходит с помощью нейронной сети Msg-Net, описанной в <a href="https://arxiv.org/pdf/1703.06953.pdf">этой статье</a>. Я обучил msg-net на очень большом количестве контентных картинок и 20 стилевых. Но в итоге, сеть научилась копировать не только эти стили, но и любой (или почти любой) другой! По исследованиям авторов статьи, большее количество учебных стилевых картинок (100 или 1000), результат не меняют. Фактически, сеть выучивает "кисти" и "палитры", а потом пытается это всё соотнести и применить в каждом конкретном случае. Кроме загрузки своей картины, можно выбрать одну из предложенных, для этого надо, следуя подсказкам, ввести номер предложенного стиля.

В ноутбуке train.ipynb, который использовался для обучения, этот процесс подробно описан со всеми особенностями.

Кроме того, есть возможность протестировать GAN на своём селфи, если всё получится, то должен измениться "Ваш цвет". Эта сеть архитектурно выполнена со многими отличиями от стандартной, кроме того "научена" на собственноручно скаченном датасете. Код сети, но на других данных можно найти <a href="https://github.com/SpiritMS/BearsGAN/blob/master/bears310.ipynb">здесь</a>, также там есть подробное описание этой сети и самого процесса обучения.

## Deploy
Сейчас этот бот работает на сервисе Heroku и связан с непосредственно этим репозиторием. Код бота написан с применением webhook, что позволяет "будить" его "по требованию".

В телеграме бота можно найти по имени DlsStyleBot

## Описание и команды
Это DLS Style transfer (telegram) bot, который является выпускным проектом Малых Михаила в Deep Learning School.
Он может переносить разные стили на Ваши фотографии. Стили Вы можете задать сами или выбрать один из предложенных. Чтобы посмотреть доступные стили, используйте команду "/styles n", где n от 0 до 21 - номер стиля.
Чтобы начать и загрузить/выбрать стилевую картинку, наберите /go.
Затем загрузите свою фотографию и Вы получите стилизованное картину в ответ!
Кроме того, Вы можете стилизовать селфи с помощью команды /gan.
Вы всегда можете посмотреть эту информацию снова, набрав  команду /help.
