数据处理步骤：

（1）读取并探索数据，绘制关键词和结果的关系图；

（2）手动修改同一条数据Target不一致数据；

（3）增加特征：包括word_count，unique_word_count，stop_word_count，url_count，mean_word_length，char_count，punctuation_count，hashtag_count（#），mention_count（@），caps_count，caps_ratio

（4）增加特征：将标签#，@和link正则提取成新的特征；

（5）文本清理：去除标点和特殊符号（>,<,&）、url，替换缩写、俚语及拼写错误等。

（6）使用nltk.stem.SnowbllStemmer()提取词干;

（7）关键词one-hot编码，url/mentions/Hashtags使用CountVectorizer向量化；

（8）Tweets进行Tf-idf编码；

（9）将上述两条的编码合并；

（10）使用pipeline建模：做归一化处理（MinMaxScaler），然后使用逻辑回归模型；

（11）模型存在过拟合，使用sklearn.feature_selection.RFECV选择特征；

（12）Public Leadboard：Score=0.80508   Top 32%

