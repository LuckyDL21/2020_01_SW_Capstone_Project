

## OpenNMT based Korean-to-English Neural Machine Translation (NMT)
This repo contains the source code and other details for a neural machine translation based on attention using pytorch. This model translates Korean into English.   

## Team

*  곽정원
*  김동영
*  김영서
*  이지환
*  조소영

## Performance

* **BLEU(Bilingual Evaluation Understudy) score** 

| BLEU | BLEU1 | BLEU2 | BLEU3 | BLEU4 | 
|---|:---:|:---:|:---:|:---:|
| **33.55** | 64.6 | 40.0 | 27.5 | 19.4 | 

* **Translation Sentence**  

#### Example 1 
```
차를 마시러 공원에 가던 차 안에서 나는 그녀에게 차였다.
```
```
> I was dumped by her in a car on the way to the park to drink tea .  
```
#### Example 2  
```
사과의 의미로 사과를 먹으며 사과했다.
```
```
> I apologize while eating an apple for the meaning of an apology .
```
#### Example 3
```
내가 그린 기린 그림은 긴 기린 그림이냐, 그냥 그린 기린 그림이냐?
```
```
> Is the giraffe I drew a long giraffe picture or just a giraffe picture ?
```
---

## Dataset

* Preprocess 
  + `Delete` the sentence with the length of 149(Korean) or more and 387(English) or more based on space.
  + `Delete` the sentence containing some special characters.
  
* Configuration 

| <center>Dataset</center> | <center>Sentences</center> | <center>Download</center> | 
|---|:---:|---|  
| Written + Spoken | 920,000 | - [AI-Hub](http://www.aihub.or.kr/) (한-영 말뭉치 AI 데이터)<br>- [Tatoeba](https://tatoeba.org/eng/downloads) (Korean - English)|

---

## How to use

```
python preprocess.py
```

```
python train.py
```


```
python translate.py -model data/model/model.pt -src data/src-test.txt -tgt data/tgt-test.txt -replace_unk -verbose -gpu 0
```

```
perl tools/multi-bleu.perl data/tgt-test.txt < data/pred.txt
```

```
pyhton gui.py
```


---

## Reference
opensource for OPEN_NMT
