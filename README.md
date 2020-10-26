# Hierachical Attention Networks For Document Classification Test

## Table of Contents

_Note: This is only a navigation guide for the specification, and does not define or mandate terms for any specification-compliant documents._

- [Sections](#sections)
  - [Title](#title)
  - [과제 개요](#과제개요)

## Sections

### Title
#### Hierachical Attention Networks For Document Classification Test
This github repository is built to test the performance of Hierachical Attention Networks For Document Classification on various test sets.

### 과제개요
네이버 쇼핑 리뷰엔 [(네이버 쇼핑 리뷰 예시)](https://search.shopping.naver.com/detail/detail.nhn?nvMid=22792140032&adId=nad-a001-02-000000108975161&channel=nshop.npla&cat_id=%EB%94%94%EC%A7%80%ED%84%B8/%EA%B0%80%EC%A0%84&NaPm=ct%3Dkgqer4gw%7Cci%3D0Ai0000qDTntH0vDv0X%5F%7Ctr%3Dpla%7Chk%3D508f26032509fd6bc3ee4b38da6b8e0dcb855ce6&cid=0Ai0000qDTntH0vDv0X_), 리뷰에 카테고리가 분류되고 어떤 단어/문장이 카테고리 분류에 영향을 주는 지 나타나 있습니다.  
어떤 알고리즘으로 구현되어 있는지 궁금하던 중 찾을 수 있는 레퍼런스가 없어 직접 구현을 시작했습니다.  
가능한 알고리즘은 1. 룰 베이스 알고리즘 2. AI 알고리즘 라 생각이 들고 AI 알고리즘 구현 방법을 고민했습니다.  
텍스트 분류 알고리즘을 찾던 중 [Hierachical Attention Networks For Document Classification](https://www.cs.cmu.edu/~./hovy/papers/16HLT-hierarchical-attention-networks.pdf)을 읽고 구현을 시작했습니다.  
[Hierachical Attention Networks For Document Classification](https://www.cs.cmu.edu/~./hovy/papers/16HLT-hierarchical-attention-networks.pdf)을 간단히 설명하자면,  
문서는 본질적으로 계층적 구조(문서는 문장으로 이루어져 있고, 문장은 단어로 이루어져 있음)를 가지고 있기 때문에, 이 구조를 이용함과 동시에 attention mechanism을 이용해 중요한 단어, 중요한 문장에 더 가중치를 줌으로써 document classification 성능 향상과 attention weight을 확인할 수 있으므로 어떤 word/sentence가 가중치를 주는지 볼 수 있습니다.  
word encoder -> word attention -> sentence encoder -> sentence attention -> decode (classification)의 구조를 가지고 있습니다.  
  
이 Repository에서는 영문 데이터인 Yahoo answers와 한글 데이터인 뉴스 데이터, 국민 청원 데이터로 실험을 진행하였습니다.  
영문 데이터 실험의 결과는 68%의 성능을 보였으며, 전처리는 keras의 tokenizer와 Glove Embedding을 사용하였습니다.  
한글 데이터는 kss.split_sentence, Okt, Kkma, sentencepiece를 사용하며 적합한 전처리 방법을 찾으려 하였으며 데이터에서 나온 단어들을 가지고 Embedding을 진행하였습니다.  
원하는 output의 모습은 글의 카테고리 분류와 attention weight이 가장 높은 문장 및 단어를 output하는 것입니다. 따라서 stopwords 제거나 문장 자체를 전처리 하는 거에 대한 고민이 많았습니다.  
국민청원 데이터의 경우, imbalance한 데이터셋이 문제일까 downsampling도 실험해보았습니다.  
다양한 실험을 하며 텍스트 데이터에 대한 익숙함을 기르게 되었고 좋은 공부를 하였습니다.  
