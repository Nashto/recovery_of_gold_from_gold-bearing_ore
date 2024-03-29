# recovery_of_gold_from_gold-bearing_ore
Creating a machine learning model for predicting recovery of gold from gold-bearing ore

Стадии добычи золота:

1. Флотация
Во флотационную установку подаётся смесь золотосодержащей руды. После обогащения получается черновой концентрат и «отвальные хвосты», то есть остатки продукта с низкой концентрацией ценных металлов.
На стабильность этого процесса влияет непостоянное и неоптимальное физико-химическое состояние флотационной пульпы (смеси твёрдых частиц и жидкости).

2. Очистка
Черновой концентрат проходит две очистки. На выходе получается финальный концентрат и новые отвальные хвосты.



Необходимо смоделировать процесс восстановления золота из золотосодержащей руды.

Эффективность обогащения рассчитывается по формуле:
Recovery = (C * (F-T)) / (F * (C - T))
где:
•	C — доля золота в концентрате после флотации/очистки;
•	F — доля золота в сырье/концентрате до флотации/очистки;
•	T — доля золота в отвальных хвостах после флотации/очистки.
Для прогноза коэффициента нужно найти долю золота в концентратах и хвостах. Причём важен не только финальный продукт, но и черновой концентрат.


Метрика качества


Для решения задачи введём новую метрику качества — sMAPE (англ. Symmetric Mean Absolute Percentage Error, «симметричное среднее абсолютное процентное отклонение»).
Она похожа на MAE, но выражается не в абсолютных величинах, а в относительных (Она одинаково учитывает масштаб и целевого признака, и предсказания).

Нужно спрогнозировать сразу две величины:

1.	эффективность обогащения чернового концентрата rougher.output.recovery;

2.	эффективность обогащения финального концентрата final.output.recovery.

Итоговая метрика складывается из двух величин.
 

