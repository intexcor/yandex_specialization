# Яндекс Специализация ML | MPII Dataset

## О проекте
В данном проекте мы работаем с датасетом MPII, который содержит 12,000 изображений человеческих поз с аннотацией действий. Этот датасет используется для обучения моделей, способных распознавать действия человека на изображениях.

![Датасет](https://github.com/user-attachments/assets/3ac9ff81-0575-4779-8902-49ef2457d153)

## Работа с датасетом
Датасет MPII представляет собой разнообразный набор изображений, который включает в себя различные позы и действия людей в различных условиях. Ниже представлена гистограмма распределения классов в датасете, которая показывает, что классы представлены неравномерно.

![Гистограмма классов](https://github.com/user-attachments/assets/00822953-5a72-46b5-869b-bdeae9ed00e5)


## Выбор модели
В процессе работы над проектом мы протестировали несколько моделей, включая:
- **DINOv2**
- **ResNet** (Resnet 18, 34, 50, 101)
- **TinyViT**
- **MobileNetV2**
- **MobileNetV3**

Каждая из моделей была оценена на основе их производительности и способности к обобщению.

## Обучение MobileNetV2 и V3
Сделав вывод о том, что MobileNet лучше остальных, так как он долго не переобучается, мы провели обучение моделей MobileNetV2 и MobileNetV3. Результаты показали, что **MobileNetV2** демонстрирует лучшие метрики по сравнению с остальными моделями, а также MobileNetV3, что делает его более предпочтительным выбором для данной задачи.

![Архитектура MobileNetV2](https://github.com/user-attachments/assets/e8bb544e-45a9-465a-a5c9-f6817384f280)


## Проверка гипотезы по выравниванию датасета
Для проверки гипотезы о выравнивании классов в датасете мы применили адаптивную аугментацию. На следующем изображении показано, как выровнялись классы после применения аугментации:

![Выравнивание классов](https://github.com/user-attachments/assets/06ea1988-b0e7-4142-be12-38006474bb4b)


Несмотря на то, что метрики остались прежними, у нас не было времени для окончательной проверки гипотезы.

## Дообучение с новым распределением данных
Мы дообучили модель MobileNetV2 на новом распределении данных, что привело к улучшению метрик. Использование большого батча также помогло стабилизировать процесс обучения. Ниже представлены графики, иллюстрирующие процесс обучения:

![График обучения](https://github.com/user-attachments/assets/7bc4442b-952f-4749-a079-9a85086b84a5)


## Выводы
В ходе проекта мы столкнулись с рядом проблем:
- Переобучение моделей.
- Нехватка оперативной памяти.
- Медленное считывание данных с диска.
- Ограниченные ресурсы и нехватка времени.

Мы пришли к выводу, что:
- Лучше использовать предобученные модели вместо обучения с нуля.
- Чем меньше датасет, тем меньше должна быть модель.
- Аугментация играет важную роль в улучшении результатов.
- Обучение на CPU может значительно замедлить процесс.

Проект продемонстрировал важность выбора правильной модели и подхода к обучению для достижения оптимальных результатов.

## Ссылки на литературу 

- [Определение положения человека на сайте NEERC](https://neerc.ifmo.ru/wiki/index.php?title=%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5_%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F_%D1%87%D0%B5%D0%BB%D0%BE%D0%B2%D0%B5%D0%BA%D0%B0)
- [Статья о MPII Human Pose Dataset](https://www.mpi-inf.mpg.de/departments/computer-vision-and-machine-learning/software-and-datasets/mpii-human-pose-dataset)
- [Хендбук яндекса по ML](https://education.yandex.ru/handbook/ml)

## Ссылки по компьютерному зрению для MPII Dataset и MobileNetV2

### MPII Human Pose Dataset
- [MPII Human Pose Dataset - Papers With Code](https://paperswithcode.com/dataset/mpii)  
  Описание и ссылки на модели, использующие MPII для оценки позы человека.
  
- [MPII Human Pose Dataset - Max Planck Institute for Informatics](https://www.mpi-inf.mpg.de/departments/computer-vision-and-machine-learning/software-and-datasets/mpii-human-pose-dataset)  
  Официальная страница с подробной информацией о датасете, включая аннотации и методологию сбора данных.

- [15 Best Free Datasets for Human Pose Estimation in Computer Vision](https://encord.com/blog/15-best-free-pose-estimation-datasets/)  
  Обзор лучших бесплатных датасетов для оценки позы человека, включая MPII.

- [MPII Human Pose Dataset на Daz 3D Forums](https://www.daz3d.com/forums/discussion/98846/mpii-human-pose-dataset-photos-of-human-poses)  
  Обсуждение и примеры изображений из MPII, полезные для художников и дизайнеров.

### MobileNetV2
- [MobileNetV2: Inverted Residuals and Linear Bottlenecks](https://arxiv.org/abs/1801.04381)  
  Исходная статья, описывающая архитектуру MobileNetV2 и её преимущества для мобильных устройств.

- [TensorFlow Model Garden - MobileNetV2](https://github.com/tensorflow/models/tree/master/research/slim/nets/mobilenet)  
  Репозиторий TensorFlow с реализацией MobileNetV2 и примерами использования.

- [Papers with Code - MobileNetV2](https://paperswithcode.com/paper/mobilenetv2-inverted-residuals-and-linear)  
  Сравнение производительности различных моделей, включая MobileNetV2, с доступными кодами.

