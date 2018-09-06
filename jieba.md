# Segmentation - jieba

## jieba

### 1. 分词函数

| func | func_explanation | para | para_explanation | return |
| :--: | :--: | :--: | :--: | :--: |
| `jieba.cut` | - | `cut(sentence, cut_all=False, HMM=True)` |cut_all 默认F(即默认精确模式)，HMM默认T| iterable generator (如果list(generator)，返回列表元素为unicode|
|`jieba.cut_for_search` | 构建搜索引擎搜索引擎倒排索引(inverted index)| `cut_for_search(sent, HMM=True)` | HMM默认T | generator |
| `jieba.lcut` | 比jieba.cut多了列表化结果 | `lcut(sent, cut_all=False, HMM=True)` | - | a list whose elements in unicode |
| `jieba.lcut_for_search` | - | - | - | - |
| `jieba.tokenize` | 切分并返回该seg在原文的起始位置 | `tokenize(sent, mode=u'default', HMM=True )`| sent必须是unicode,在str引号前加一个u即可；mode取值为default或者search（default精确切分）| generator,里面ele是tuple(seg,start,end) |
| `jieba.load_userdict` | 使用自定义词典 | `load_userdict(file)` | file必须为UTF-8;file必须和自带dict.txt格式一样（`词语\s词频\s词性`），词性可省略，词频越大成词概率越大 | - |
| `jieba.add_word` | 给词典中增加词汇（自带词典？） | `add_word(word, freq=None, tag=None)` | word(str),freq(int)可省略,tag(str)可省略 | - |
| `jieba.del_word` | 删除词典中的词汇 | del_word(word) | - | - |
| `jieba.suggest_freq` | 调节词语的词频，用于将一个词汇中的字符分开或合并 | `suggest_freq(segment, True)` 2nd para直接写T/F| segment某一词汇被希望的切分形式；tune为True时调整词频。('seg','seg')单个元素也可以用元组。 | 调用此函数后，再分词时可以使`HMM=False`,以防干扰 |


### 2. 词性标注
 posseg(a library) 包含以下pos tagging functions
```python
 import jieba
 from jieba import posseg
 ```
 
 | func | func_explanation | para | para_explanation | return |
 | :--: | :--: | :--: | :--: | :--: |
 | `jieba.posseg.cut` | 同时分词&词性标注 | posseg.cut(sent,HMM=True) | pair对象 `pair(u'word',u'tag')` NB中和说明不一致 |
 | `lcut` | 返回列表化结果 | `posseg.lcut(sent, HMM=True)` | - | - |
 




