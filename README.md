# hse21_H3K4me1_ZDNA_human

Проект по Биоинформатике.
Версия Генома - hg19

# Результаты

## Анализ пиков гистоновой метки
### Гистограмма длин участков для каждого эксперимента до и после конвертации к hg19 версии генома, а также после фильтрации

#### ENCFF572NWJ

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF572NWJ.hg38.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.filtered.png)

#### ENCFF952QRP

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF952QRP.hg38.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF952QRP.hg19.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.ENCFF952QRP.hg19.filtered.png)

### Графики с расположением пиков гистоновой метки относительно аннотированных генов. 

#### ENCFF572NWJ

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/chip_seeker.H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.filtered.plotAnnoPie.png)

#### ENCFF952QRP

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/chip_seeker.H3K4me1_HeLa-S3.ENCFF952QRP.hg19.filtered.plotAnnoPie.png)

### Объединение двух наборов отфильтрованных ChIP-seq пиков с помощью утилиты bedtools merge.

## Анализ вторичной структуры ДНК

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.DeepZ.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/chip_seeker.DeepZ.plotAnnoPie.png)

## Анализ пересечений гистоновой метки и структуры ДНК

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.intersect_with_DeepZ.png)
