# 电视动画播出信息

自 1959 年至 2018 年 1 月日本电视动画的播出信息。

## 数据来源
原始数据来自于[テレビドラマデータベース](http://www.tvdrama-db.com/)，选取了连续电视动画。并通过以下网站补充及修正数据，重要性按先后顺序递减：
* [日本维基百科](https://ja.wikipedia.org/wiki/%E3%83%A1%E3%82%A4%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8)
* [映画データベース - allcinema](http://www.allcinema.net/prog/index2.php)
* [アニメ情報調査室](http://www.anime.marumegane.com/)
* [MyAnimeList.net](https://myanimelist.net/)
* [メディア芸術データベース](https://mediaarts-db.bunka.go.jp/?locale=ja&display_view=sp)
* 动画官方网站

## `anime_onair_data`数据说明
数据为纯文本文件，采用制表符（ tab ）分隔字段。

### id
每条记录的唯一标识，没有实质意义，数据维护用。

### tid
每部作品的唯一标识，最长 5 位数，源自[テレビドラマデータベース](http://www.tvdrama-db.com/)。部分作品 ID 为 6 位数并以`00`结尾，为[テレビドラマデータベース](http://www.tvdrama-db.com/)缺少的作品。 

### title
作品的标题，来自[テレビドラマデータベース](http://www.tvdrama-db.com/)。标题中的`(1)`、`(2)`对应`第一季`等内容。

### ori_work
原作类型。
* original: 原创作品
* comic：漫画
* novel：小说
* light_novel：轻小说
* game：游戏
* galge：美少女游戏，包括全年龄和 18 禁
* media_mix：多媒体策划，如《死后文》
* goods：玩具、文具等
* game_book：游戏书，那种如果 ×× 就翻到第 n 页的书，如《女王之刃》
* movie：真人电影，如《七武士》
* character：角色，如三丽鸥的 Hello Kitty、初音未来等
* picture_book：图画书，即常说的绘本
* play：戏剧，如莎士比亚的作品
* tale：童话、寓言

### st_date、ed_date
首播日期，结束日期。
日期格式为`YYYY/MM/DD`。

### st_day
播出日。
使用日本的曜日记法。对应如下：
* 日（曜日）：星期日
* 月（曜日）：星期一
* 火（曜日）：星期二
* 水（曜日）：星期三
* 木（曜日）：星期四
* 金（曜日）：星期五
* 土（曜日）：星期六

### st_time、ed_time
首播时间，结束时间。
采用 30 小时制，一天为 30 小时。比如`1996/01/03`凌晨`01:00`播出的作品，会记录为`1996/01/02`年的`25:00`播出。需要 24 小时制时间的，注意转换。

### channel、ch_name
首播电视台的简称和名称。如果同时期有多个电视台播出的，标记核心台。

### type
* earth：地上波
* cs：采用通讯卫星广播的卫星电视台
* bs：采用广播卫星广播的卫星电视台
* nhk：NHK 系的电视台
* uhf：所有独立电视台，不光是超短波广播电视台。
* web：互联网电视。

## `anime_production_data`数据说明
数据为纯文本文件，采用制表符（ tab ）分隔字段。

### id
每条记录的唯一标识，没有实质意义，数据维护用。

### tid
每部作品的唯一标识，与`anime_onair_data`中的 tid 对应。

### title
作品的标题。

### company
出品公司的名称，可能是简称，也可能是全称。要注意部分公司曾经改名，会使用我觉得方便的名字。
* `NBCユニバーサル・エンターテイメントジャパン`在 2005 至 2007 期间实际上都是叫`ジェネオン エンタテインメント株式会社`或`Geneon`，但我一律使用了 NBC 的名称
* `KING RECORD`实际上很多作品中是使用`STARCHILD`的名义，但由于`STARCHILD`是`KING RECORD`的品牌公司，因此一律使用了`KING RECORD`
* `東芝エンタテインメント`在 2007 年由`博報堂DYメディアパートナーズ`收购为全资子公司，并改名为`ショウゲート（ Showgate ）`，但以`ショウゲート`名义投资的作品我都直接标注了`博報堂DYメディアパートナーズ`。

**必须注意，标注的公司有的是可查的出品委员会成员公司，有的是从策划人、制片人所属推测的，不一定正确。对这方面数据有精度要求的，请自行核实。**

### business
出品公司的主营业务。
* video producer ：映像出品。即联系光盘制造商把映像生产成光盘，然后联系流通商送到不同门店销售的公司。
* anime production ：动画出品。和映像出品一样，但住营动画。
* record company ：唱片公司。
* books wholesaler ：出版物流公司，负责把出版物从出版社运送到各个书店。日本出版物流势力很大，几乎是专营的，出版社和书店通常无法自己干。
* anime maker ：动画制作公司。
* tv station ：电视台。
* right management ：著作权管理公司。
* talent management ：艺人事务所。
* game maker ：游戏制作公司，光制作游戏的，没有发行业务。
* disk maker ：光盘生产商，把内容制作成光盘。
* publishing company ：出版社。
* goods wholesale ：周边销售商。
* film producer ：电影发行商。
* ad agent ：广告代理公司。
* game company ：游戏公司。
* video post production ：映像后期制作公司。
* pachinko maker ：柏青哥等赌博机制造商。
* it company ：IT 公司。
* radio station ：电台。
* ad maker ：广告制作公司。
* sound maker ：音响公司。
* video exporter ：映像出口商，把映像制品卖到日本境外。
* video wholesale ：映像销售商，销售映像制品的公司。
* bookshop ：书店。
* mobile network operator ：移动网络运营商。
* art auction ：美术品拍卖公司。
* exhibition curation ：策展公司，开办各种展会的。
* production fund ：映像出品基金，《甲贺忍法帖》特有。
* goods producer ：商品出品公司，开发、推广、销售商品的公司。
* tv maker ：电视节目制作公司。
* program sale ：电视节目销售公司，把一个电视台的电视节目卖给其他电视台。
* wholesale ：商品批发商，就是通常意义上的商品，类似阿里巴巴，不过是线下的。

## 注意事项
1. 1996 年之前的数据缺失比较严重。
2. `anime_onair_data`仅有小部分数据（ 120 条左右）经过人工补充和核对，其余数据皆为原始数据。
3. `anime_production_data`中所有数据都是人工收集，标注的公司有的是可查的出品委员会成员公司，有的是从策划人、制片人所属推测的，不一定正确。对这方面数据有精度要求的，请自行核实。
4. 人工补充和核对数据全部来源于网络。
