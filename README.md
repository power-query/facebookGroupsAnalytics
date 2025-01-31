
# Внимание, в связи с [изменениями политики работы с даннными facebook от 04.04.2018](https://developers.facebook.com/docs/graph-api/changelog/breaking-changes/#groups-4-4), через api больше нельзя получать информацию об авторе поста, авторах комментариев, полученных реакциях. Таким образом по состоянию на 7.04.2018 данная BI система бессмыслена. 

![](https://content.screencast.com/media/44ca71ba-faec-4816-8d95-97c1cf5c152f_9d700cb2-87df-433c-8403-c813c6a51c87_static_0_0_2018-04-07_15-09-15.png)


Старое readme:
# facebookGroupsAnalytics

Power BI for Facebook Group Analytics

- [Видео инструкция][1] по bi-системе на bi-tv.ru
- [Ссылка][2] на статью Gil Raviv, где он рассказал, как при помощи List.Generate круто разбирать JSON от Facebook. 
- [Ссылка][3] на обсуждение BI-системы в группе ["Power BI, Excel для интернет-маркетинга и не только"][4]
- [Ссылка][6] на опубликованную BI-систему

# Извлечение кода мер Dax и скриптов M #

В качестве эксперимента решил попробовать код функций публиковать отдельно на github. Нашел в интернетах, что меры Dax можно извлечь при помощи Dax Studio. [Источник](https://exceleratorbi.com.au/dmv-extract-measures-power-pivot/)

```
select  [TABLE],
        OBJECT as ColumnName,
        Expression
     
from $SYSTEM.DISCOVER_CALC_DEPENDENCY

where OBJECT_TYPE = 'CALC_COLUMN' and
REFERENCED_OBJECT_TYPE = 'COLUMN'
```

Код скриптов в M был извлечен при помощи программы [Power BI Helper](http://radacad.com/power-bi-helper)

[![][image-1]][6]

[1]:	https://www.facebook.com/bitvru/videos/1719557358338051/
[2]:	https://datachant.com/2016/06/27/cursor-based-pagination-power-query/
[3]:	https://www.facebook.com/groups/Excelforever/permalink/1708646089465042/
[4]:	https://www.facebook.com/groups/powerBiForever/
[5]:	http://bit.ly/2se4TcA
[6]:	https://app.powerbi.com/view?r=eyJrIjoiYjg3MGQ3OTktOWQxMy00NGE2LWI4MDYtNWMzNjA0MTU4MjgxIiwidCI6Ijg0MGM1ZDE3LTA2ZjUtNDVlMC1iOTYyLWNjOTE1Zjg1NWU4MyIsImMiOjl9

[image-1]:	https://content.screencast.com/media/7aa2826b-cb5b-45cc-a304-476271e788f7_9d700cb2-87df-433c-8403-c813c6a51c87_static_0_0_2017-10-19_00-48-40.png
