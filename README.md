# hse21_H3K4me1_ZDNA_human

Проект по Биоинформатике.
Версия Генома - hg19

# Результаты

## Анализ пиков гистоновой метки
### Гистограмма длин участков для каждого эксперимента до и после конвертации к hg19 версии генома, а также после фильтрации

Команды для скачивания

wget https://www.encodeproject.org/files/ENCFF572NWJ/@@download/ENCFF572NWJ.bed.gz

zcat ENCFF572NWJ.bed.gz | cut -f1-5 > H3K4me1_HeLa-S3.ENCFF572NWJ.hg38.bed

wget https://www.encodeproject.org/files/ENCFF952QRP/@@download/ENCFF952QRP.bed.gz

zcat ENCFF952QRP.bed.gz | cut -f1-5 > H3K4me1_HeLa-S3.ENCFF952QRP.hg38.bed



Команды для конвертации к нужной версии генома(hg19)

wget https://hgdownload.cse.ucsc.edu/goldenpath/hg38/liftOver/hg38ToHg19.over.chain.gz

liftOver H3K4me1_HeLa-S3.ENCFF572NWJ.hg38.bed hg38ToHg19.over.chain.gz H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.bed H3K4me1_HeLa-S3.ENCFF572NWJ.unmapped.bed

liftOver H3K4me1_HeLa-S3.ENCFF952QRP.hg38.bed hg38ToHg19.over.chain.gz H3K4me1_HeLa-S3.ENCFF952QRP.hg19.bed H3K4me1_HeLa-S3.ENCFF952QRP.unmapped.bed 

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

Команда для объединения

cat  \*.filtered.bed  |   sort -k1,1 -k2,2n   |   bedtools merge   >  H3K4me1_HeLa-S3.merge.hg19.bed


### Визуализация в геномном браузере

track visibility=dense name="ENCFF572NWJ"  description="H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.filtered.bed"

https://raw.githubusercontent.com/ryandrey/hse21_H3K4me1_ZDNA_human/main/data/H3K4me1_HeLa-S3.ENCFF572NWJ.hg19.filtered.bed

track visibility=dense name="ENCFF952QRP"  description="H3K4me1_HeLa-S3.ENCFF952QRP.hg19.filtered.bed"

https://raw.githubusercontent.com/ryandrey/hse21_H3K4me1_ZDNA_human/main/data/H3K4me1_HeLa-S3.ENCFF952QRP.hg19.filtered.bed

track visibility=dense name="ChIP_merge"  color=50,50,200   description="H3K4me1_HeLa-S3.merge.hg19.bed"

https://raw.githubusercontent.com/ryandrey/hse21_H3K4me1_ZDNA_human/main/data/H3K4me1_HeLa-S3.merge.hg19.bed


## Анализ вторичной структуры ДНК

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.DeepZ.png)

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/chip_seeker.DeepZ.plotAnnoPie.png)


## Анализ пересечений гистоновой метки и структуры ДНК

Команда для пересечения

bedtools intersect -a DeepZ.bed -b H3K4me1_HeLa-S3.merge.hg19.bed > H3K1me1_HeLa-S3.intersect_with_DeepZ.bed

![alt text](https://github.com/ryandrey/hse21_H3K4me1_ZDNA_human/blob/main/images/len_hist.H3K4me1_HeLa-S3.intersect_with_DeepZ.png)


### Визуализация в геномнои браузере

track visibility=dense name="DeepZ"  color=0,200,0  description="DeepZ"

https://raw.githubusercontent.com/ryandrey/hse21_H3K4me1_ZDNA_human/main/data/DeepZ.bed

track visibility=dense name="intersect_with_DeepZ"  color=200,0,0  description="H3K4me1_HeLa-S3.intersect_with_DeepZ.bed"

https://raw.githubusercontent.com/ryandrey/hse21_H3K4me1_ZDNA_human/main/data/H3K4me1_HeLa-S3.intersect_with_DeepZ.bed

## Ассоциация с ближайщими генами и GO-анализ


