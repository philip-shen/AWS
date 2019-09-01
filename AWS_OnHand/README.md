# Purpose
Take note of On Hand issue on AWS

# Table of Content



# Reference
* [Yuting Chou‎ 發文到 Backend 台灣 (Backend Tw)]()  
```
想請問大家：如果公司規模小，平常要如何累積處理大流量的經驗呢？

(可能我中文用詞不當，導致看到幾則留言都是偏向「處理大量資料」的方向😱
我直接拿出實際上JD的範例好了：
例1: Experience with developing complex software systems scaling to millions of users with production quality deployment, monitoring, and reliability

例2: Experience in design and development of large-scale distributed systems is preferred
)

OS1: 為了想要有處理高流量的經驗，所以想要進大公司；可是大公司的面試官又會覺得你雖然有看起來優秀的後端工作經歷，可是卻沒有處理過流量大的經驗！？

OS2: 似乎熟悉AWS上面的best practices還是不太夠啊？！
（補充：我已經有AWS architect associate的證照，而且production都是部署在AWS上面）

===額外附贈失敗面試遇到的問題集：
1. 某新加坡商的義大籍（口音超重）架構會問：
如何在億萬筆隨機數字資料中，找尋一個數字是否存在？請給出一個你認為時間複雜度最低的方法。
（補充：因為後來延伸有提到如果有1 billion的隨機10位數字放在hash會佔多少記憶體空間？有什麼缺點？所以我事後才會猜測對方可能想聽到bloom filters吧！）

=> 我後來查資料，猜想他應該是想要我可以回答出bloom filters這個答案

2. 某瑞典新創：
如何在讓你設計的api去避免重複交易的情況？
（補充：這其實是pair programming時遇到的問題；當時的情景是，已經有一個現成的交易api了, 如何修改既有的api去達到避免重複交易。對方一直著重在express js api裡面怎麼實作😱）

=> 我當時回答的是給一個unique token去辨別是否為統一使用者發出的重複交易請求；但看起來她不是很滿意。後來才知道有Idempotency Key這種設計。（有興趣的可以參考：https://blog.frost.tw/posts/2017/10/30/The-design-of-Stripe-s-Idempotency-Keys/）
```

```
Chauyan Wang 多練習 多上來找人討論 以我的經驗來看 (目前人在美國) 我覺得你已經有機會面試, OS1 不是問題, 因為面試官會知道你目前的狀況, OS2就是多練習, 組個group 討論這樣, 會有所幫助, 祝一切順利 找到自己的理想工作, 我並非 backend engineer 只是目前有幫忙做 backend 的東西

Yuting Chou Chauyan Wang 剛剛我有增加OS2的補充了。

基本上很熟AWS的部署，只是貌似有AWS實戰經驗不太夠。

目前我遇到比較沒有OS1問題的真的只有歐美商.......
亞洲的新創感覺就是要找即戰力而已😂😂

Chauyan Wang 不過我看討論串很有意思, 有個重點是, 你能不能跟你的 interviewer 溝通, 因為做法很多種, 有時候找到 solution 跟 compromise 也很重要
```

```
Lichi Chiang 1. 某新加坡商的義大籍（口音超重）架構會問：
如何在億萬筆隨機數字資料中，找尋一個數字是否存在？請給出一個你認為時間複雜度最低的方法。

開一塊ram去做bit存取就好
用的容量最小,速度最快
100Mbit 就可以處理億級的數字,可以即刻算出數字是否存在
目前我還想不出比這快的方式了

2. 某瑞典新創：
如何在讓你設計的api去避免重複交易的情況？

避免重複交易的方法非常多種
有用transaction table , 有用pl/sql , 有用socket lock
有用file lock
答案非常多種,視情況使用.
```
```
首先，我覺得一般來說你是要跳槽才有辦法遇到大流量的公司，
但大流量公司我覺得大部分都是考很多扎實的觀念，實務中用的各家服務只是拿來說市場上有這些服務可以舉例而已。

個人認為第一題他可能就只是要考你hash的問題而已，但hash之後的碰撞要怎麼處理，前面資料如何儲存成你想要存取的方式，或是consistent hashing，我覺得比較是他想要考的，你看Bloom filters也只是hash的延伸而已，而且各個公司都有自己的框架。
他想問的不一定就是要”正確答案“或他們公司或面試官本身知道的解決方式，因為各個產品或框架基本解決方法都是不變的。

另外來說，Bloomberg主要的產品也沒有在AWS上面跑，他有自己個框架在跑他的產品，ＡＷＳ的服務也只是你在跟面試官提出你的解決方案中，目前市場已經有哪些產品可以用。

個人國外面試的經驗而已。

你可以參考看看這個課程：
https://www.educative.io/collection/5668639101419520/5649050225344512?fbclid=IwAR0sOzPk1Tzyv4LBhbrrNZ710JBRHR7CwkFoyJ75FqFqt4cmDoFTRW11hjQ
```
```
Triton Ho 認真答你：

會問你高流量經驗的主管，其實也沒面對過多少高流量的。
結果這類面試都是最後流於灌水打嘴砲的……

另外，在C10K的世界，其實系統架構跟小公司沒什麼太大分別的
只是嘛，小公司犯錯時單純CPU高一點點（因為流量太少）
C10K時便直接趴掉

簡單而言囉，高流量世界就是不要犯錯，所有的基本功夫全要做好
然後你可以很安全地活到C100K的（更上的請問Google他們）

Yuting Chou Triton Ho 真的！我自己後來思考得出的結論是：

可能這些主管只有概念自己沒有經歷過，所以想要找一個即戰力的隊員來讓自己的團隊好像很厲害！
```
```
Triton Ho 所謂的基本功夫嘛（包括，但不限於）

像是connection pool有沒有建好？
LB層設定是否正確？
CDN呢？
http header有正確嗎？
Redis cache TTL有根據業務做好嗎？
有用jwt作access token嗎？

以２０１９標準而言，這些功夫全都不是什麼高大上的東西
（至少你聽我免費淺談我全有說過）

Yuting Chou Triton Ho 某一個砲我的主管，對於如何學習distributed system,居然建議我去讀erlang的paper........

(他本人表示他是從矽谷出來的，以前待IBM)
```
```
Triton Ho 另外，怎知對方在打嘴砲還是真的實戰過的：

一般用嘴巴來工作的人
天天都滿嘴Paxos / Raft algorithm，然後整天都說在一台machine上開5000個thread這種新人嚇死老手笑死的幹話
```
```
Yuting Chou Triton Ho 我遇到的狀況是...

對方不跟你講細節，而是直接說：我公司的流量很高，可是你沒有處理的經驗耶！😭
```
```
Hu Max 這類的問題真有趣，不曉得我的想法是否正確

雖然這兩題是不同公司問的，但覺得你遇到的問題集，好像有點關聯，
似乎都跟『當交易沒有正常結束，如何快速恢復交易』
1. 透過你所說的設計方法，避免重複交易
2. 因為 1 的需求，需要快速找到該 key，並調出資料，以繼續交易流程

另外我有點好奇就是 Bloom filter 應用場景，除了在『購買』的行為中，還有什麼複雜的場景應用？影片中斷，從中斷點恢復？建立搜尋清單的比對？
```


* []()  
![alt tag]()

# h1 size

## h2 size

### h3 size

#### h4 size

##### h5 size

*strong*strong  
**strong**strong  

> quote  
> quote

- [ ] checklist1
- [x] checklist2

* 1
* 2
* 3

- 1
- 2
- 3
