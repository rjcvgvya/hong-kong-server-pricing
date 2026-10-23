# hong-kong-server-pricing# 香港伺服器租用公司：三網回程線路與 GoMami 全系列套餐價格整理，按場景選對方案不花冤枉錢

搜「香港伺服器租用公司」的人，真正想解決的問題通常只有一個：伺服器放在香港，大陸用戶連上來要快、要穩，尤其是晚上九點的尖峰時段。目前市場上能滿足這個需求的產品分兩類：一類是傳統 IDC 賣的實體獨服和主機托管，一類是近幾年興起的「大陸方向優化」VPS。GoMami Networks（gomami.io）屬於後者，主打電信 CN2 GIA、聯通 AS9929、移動 CMIN2 三網回程精品線路，官網標稱香港到大陸 RTT 低於 50ms。這篇文章把它的全部套餐、價格、實測數據、優惠碼和退款政策整理在一起，幫你判斷它到底適不適合你。

> **選購速覽**
> - 一般網站、WordPress、容器應用：HKG Pulse 系列，入門 Nano $49/月，Mini（2核4GB）$59/月
> - 遊戲伺服器、即時應用等吃單核性能的場景：Peak X5 Mini（AMD 9950X），$59/月
> - 要最新硬體（Zen 5、DDR5、Gen5 SSD）：HKG Turin 系列，$69/月起
> - 新購實例 24 小時內可全額退款（官文文件明確，限首次購買、每用戶一次）
>
> 👉 [查看 GoMami 香港及其他節點套餐的當前價格](https://bit.ly/Gomami)

## 挑香港伺服器，線路比 CPU 更值得先看

香港機房多如牛毛，真正拉開差距的是回程線路。很多標著「中國優化」的主機，下午測延遲很漂亮，一到晚高峰延遲翻倍，而且往往只有一個電信方向跑得好，聯通和移動用戶照樣卡。GoMami 的核心賣點就是把三個運營商的回程一次做齊：

- **CN2 GIA（AS4809）**：電信精品骨幹，香港到廣東低於 50ms（官網標稱口徑，未經獨立核驗），從美西回來約 148–150ms
- **AS9929（CUII）**：聯通精品國際線路，晚高峰吞吐更穩定，美西回程約 160–163ms
- **CMIN2（AS58807）**：移動的較新國際網路，美西回程約 162–166ms

多份第三方評測的共同結論是：晚高峰能否保持標稱速度，正是這家在三網優化上拉開差距的地方。以洛杉磯線為例，第三方 DigVPS 對 LAX Pulse Mini 做了長期路由監測，確認電信 CN2、聯通 9929、移動 CMIN2 三網回程各自走精品線，並在持續觀察後把評級上調為 E2，原話是「經過一段時間的觀察，產品穩定性不錯」。

防護方面有個容易忽略的細節：按官方文件的說法，預設附帶的是 best-effort（盡力而為）級別的 DDoS 防護，600 Gbps 屬於可選的高級清洗服務。官網行銷頁寫的「最高 600 Gbps」是上限口徑，對防護有硬性要求的業務，下單前建議先問清楚自己那一檔實際包含什麼。

## GoMami 香港節點全套餐與價格

香港節點目前有四條產品線：Turin（EPYC 9575F，Zen 5）、Peak X5（Ryzen 9 9950X）、Pulse（EPYC 7763）和面向重度負載的 Forge 獨立伺服器。以下為月付價格，整理自官網與第三方彙整資料：

| 套餐 | vCPU／記憶體 | NVMe | 流量（出）／埠 | 月付 | 購買 |
| --- | --- | --- | --- | --- | --- |
| Turin.Mini | 2核／4GB | 100GB | 1TB／2Gbps | $69 | [ 購買](https://bit.ly/Gomami) |
| Turin.Air | 4核／8GB | 140GB | 2TB／2Gbps | $129 | [ 購買](https://bit.ly/Gomami) |
| Turin.Pro（支援 Windows） | 6核／16GB | 180GB | 5TB／5Gbps | $299 | [ 購買](https://bit.ly/Gomami) |
| Turin.Ultra（支援 Windows） | 12核／32GB | 220GB | 10TB／5Gbps | $599 | [ 購買](https://bit.ly/Gomami) |
| Peak X5.Mini | 2核／4GB | 40GB | 1TB／2Gbps | $59 | [ 購買](https://gomami.io/aff.php?aff=415&pid=1) |
| Peak X5.Air | 4核／8GB | 60GB | 2TB／2Gbps | $99 | [ 購買](https://bit.ly/Gomami) |
| Peak X5.Pro | 6核／16GB | 80GB | 5TB／5Gbps | $199 | [ 購買](https://bit.ly/Gomami) |
| Pulse.Nano | 2核／2GB | 40GB | 500GB／1Gbps | $49 | [ 購買](https://bit.ly/Gomami) |
| Pulse.Mini | 2核／4GB | 60GB | 1TB／1Gbps | $59 | [ 購買](https://bit.ly/Gomami) |
| Pulse.Air | 4核／8GB | 80GB | 2TB／1Gbps | $119 | [ 購買](https://bit.ly/Gomami) |
| Pulse.Pro（支援 Windows） | 8核／16GB | 100GB | 5TB／3Gbps | $269 | [ 購買](https://bit.ly/Gomami) |
| Pulse.Ultra（支援 Windows） | 16核／32GB | 300GB | 10TB／5Gbps | $499 | [ 購買](https://bit.ly/Gomami) |

一個需要留意的數據衝突：官網卡片把 Peak X5.Air 標為 4 核，但同系列 Mini 實測確認是 2 核（9950X 本身是 16 核處理器），Air 實際分配到的核心數建議以下單頁顯示為準。另外官方文件提到 Turin 和 Pulse 線年付通常比月付省 15%–20%，長期使用可以先算一下年付總帳。

Turin 系列全部配 PCIe Gen5 U.2 SSD 和 DDR5 6400MHz 記憶體，睿頻最高 5.0GHz，是目前最新架構的旗艦線；Peak X5 走 9950X 的高主頻路線，價格比同檔 Turin 便宜，代價是儲存空間明顯更小。

需要整機不搞鄰居噪音的，看 Forge 獨立伺服器線（EPYC 7663，56核112執行緒）：

| 套餐 | 記憶體／儲存 | 流量／埠 | 月付 | 購買 |
| --- | --- | --- | --- | --- |
| Forge Mini | 128GB／960GB NVMe | 10TB／2Gbps | $399（另收一次性 $68 安裝費） | [ 購買](https://bit.ly/Gomami) |
| Forge Air | 256GB／4TB NVMe | 20TB／2Gbps | $699（另收一次性 $68 安裝費） | [ 購買](https://bit.ly/Gomami) |

## 第三方實測：9950X 的 CPU 是滿血的，但 IO 被鎖了一半

這是大多數只抄規格表的文章不會告訴你的部分。測評部落格 catcat.blog 的 Sharon 在 2025 年 8 月實測了 HKG.Peak.X5.Mini（Debian 12，KVM）：

- Geekbench 5：單核 2566／多核 4520；Geekbench 6：單核 3419／多核 5974
- PassMark CPU Mark：8451，記憶體延遲 65ns
- fio 4k 混合讀寫：讀 399 MB/s／寫 400 MB/s
- dd 寫入 10GiB：846 MB/s

CPU 分數接近滿血 9950X，作者原話是「機器相比 AMD 7763 系列是鎖了 IO 的，砍了對半。CPU 是滿血 9950X 的分數」，同樣用 fio 生成 10G 測試檔，和 7763 版差距約三倍。另外這台實測機 IPv6 未開通（僅單一樣本，不代表全部方案），流量只計出方向。

實際結論：跑 WordPress、API、遊戲伺服器這類應用完全夠用；但如果你要做大量磁碟讀寫的資料庫或頻繁編譯任務，Pulse 系列或 Forge 獨服的 IO 更划算。同月對 HKG.Pulse.Mini（7763）的實測也值得一提：dd 寫入 2.3 GB/s，10GB 檔案從廣東電信直取能跑滿頻寬。想自己驗證的話，👉 [開通 Peak X5 Mini（AMD 9950X）方案](https://gomami.io/aff.php?aff=415&pid=1)後，記得在 24 小時退款期限內把 dd 和 fio 都跑一遍再決定去留。

## 洛杉磯節點：三網雙向精品，另有專屬八折碼

如果你願意接受 150ms 左右的延遲換更低價格，GoMami 的洛杉磯線是目前產品矩陣裡規格最激進的一段：三網**雙向**都走 CN2 GIA／9929／CMIN2 精品，而不只優化回程。2026 年的第三方資料顯示實測三網回程約在 148–166ms 區間，被評為洛杉磯 CN2 GIA 陣營的第一梯隊水平。

六款套餐的月付原價與「Hi,LAX」八折後價格如下：

| 套餐 | vCPU／記憶體 | NVMe／埠 | 流量（出） | 原價／折後月付 | 購買 |
| --- | --- | --- | --- | --- | --- |
| Nano | 2核／2GB | 40GB／1Gbps | 1TB | $29 → $23.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulsenano) |
| Mini | 2核／4GB | 60GB／1Gbps | 2TB | $59 → $47.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulsemini) |
| Air | 4核／8GB | 80GB／2Gbps | 4TB | $129 → $103.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulseair) |
| Pro（可裝 Windows） | 6核／16GB | 100GB／3Gbps | 8TB | $259 → $207.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulsepro) |
| Ultra（可裝 Windows） | 12核／32GB | 300GB／5Gbps | 15TB | $599 → $479.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulseultra) |
| Titan（可裝 Windows） | 12核／32GB | 600GB／10Gbps | 30TB | $999 → $799.2 | [ 購買](https://gomami.io/aff.php?aff=415&url=/store/lax-pulse/laxpulsetitan) |

比起亞洲節點，LAX 的流量配額明顯更大（Nano 就有 1TB，亞洲 Pulse Nano 只有 500GB），CPU 為 EPYC 7K62（3.3GHz）。有測評對 Nano 實測後稱「新開的機器 IP 質量都很好，流媒體解鎖、AI 也都全解鎖」，適合拿來做需要乾淨 IP 的 AI 相關業務。

## 優惠碼與實際入手成本

GoMami 不碰 $5/月的低價市場，定位在中高端，優惠碼是目前唯一確定的省錢途徑，而且各碼適用範圍不同，別混填：

- **Hi,LAX**：僅適用 LAX Pulse 全部六款，循環 8 折（續費同價，不是首月特價），月付／季付／年付均可。在購物車「Review & Checkout」頁的 Promo Code 輸入框填寫，金額即時刷新。
- **GOMAMI365**：覆蓋全部產品線（香港／日本／新加坡／洛杉磯），循環 8 折，但**僅年付生效**。
- **HappyBirthday**：2025 年 8 月測評中的首發碼，當時可把 $59 的 Peak X5 Mini 壓到 $50.15/月、$39 的 Pulse Mini 壓到 $33.15/月。這個碼出自一年多前的測評，現在是否有效以結帳頁實際顯示為準——試一下不花錢，填了沒折扣就說明已過期。

優惠碼有效期隨時可能調整，所有折扣以下單時購物車顯示為準。

## 退款、付款方式與超流量的真實規則

退款政策這次直接查了官方文件，比行銷頁的說法具體得多，也有幾個必須知道的限制：

- 新購實例激活後 **24 小時內**可全額退款，原路退回；僅限首次購買，每位用戶限一次，續費訂單一律不退
- 超過 24 小時不退；因違反服務條款被終止、以及因 DDoS 導致 IP 被 blackholed 的情況也不退
- 申請路徑：工單系統選 Billing 類別提交；退款批准後**對應實例和數據會被立即永久刪除**，官方明確提醒申請前先備份
- 到賬時間：支付寶和加密貨幣 1–3 個工作日，信用卡 5–10 個工作日

付款方式支援信用卡（Stripe）、支付寶和加密貨幣。計費週期有月付、季付、半年付、年付四檔；到期當天伺服器即暫停且無寬限期（數據保留，付款後恢復），逾期 5 天服務終止、數據可能無法恢復——建議預存帳戶餘額用於自動續費。

超流量的處理方式也有明確說法（以 LAX 線公開說明為準）：當月出向流量到頂後埠限速至 20 KB/s，下個計費週期恢復，不停機、不額外扣費。香港線是否同樣處理，下單前向客服確認一句即可。配合官網標榜的單向計費（只算出向），日常分發類業務的實際可用流量比表面數字更寬鬆。

## 和傳統香港伺服器租用公司比，差在哪

搜這個關鍵詞時你會遇到大量傳統本地 IDC，例如 Dataplugs、Varidata、Advanhost、newsbook、CommuniLink 等。它們的主業是實體獨服和主機托管：從公開價目表看，newsbook 的入門獨服 B29 約 HK$880/月（需預繳一年），icon-centre 2022 年價目表上多數方案在 HK$1300/月以上。要說明的是，這些是實體獨服／托管的價格口徑，和 VPS 不完全可比——你買到的是整台物理機和完整埠。

兩條路怎麼選：需要整台物理機、大頻寬獨佔、把機器放進機房託管，傳統 IDC 合適；用戶在大陸、預算幾十到幾百美元、要開機即用還自帶備份的，GoMami 這類優化 VPS 的單位成本明顯更低，而且開通免費即時，不滿意還有 24 小時退款兜底。

## 常見問題

**流量是雙向計費嗎？** 不是。實測機和官方說明都確認只計出方向，入站不佔額度；超量後限速 20 KB/s 至下週期，不停機不扣費。

**能裝 Windows 嗎？** 可以，但限 Pro 及以上檔位：Turin.Pro、Turin.Ultra、Pulse.Pro、Pulse.Ultra，以及 LAX 的 Pro／Ultra／Titan。入門檔預設 Linux。

**有 IPv6 嗎？** 2025 年 8 月的香港實測中 IPv6 未在線，只有單一樣本。如果你的業務依賴 IPv6，下單前直接問客服確認。

**路由自己怎麼驗證？** 官方提供 Looking Glass（lg.gomami.io），下單前就能自查三網去回程路由，不用等開機後再發現線路不對。

## 按你的情況怎麼選

- 預算敏感的一般建站：Pulse Nano（$49）夠用，別為用不到的核心多花錢
- 正經跑業務網站、稍微有點流量：Pulse Mini 或 Pulse Air，儲存比 Peak X5 大一截
- 遊戲伺服器、即時對戰、任何吃單核的東西：Peak X5 Mini（$59），9950X 的單核分數在香港 VPS 裡屬於第一梯隊
- 資料庫、AI 推理、想要最新架構：Turin 系列，Zen 5 加 Gen5 SSD，年付還能再省 15%–20%
- 要 Windows 或 16 核以上：直接看 Pulse.Pro／Ultra 或 Turin.Pro／Ultra
- 大陸用戶為主但預算卡得很緊：洛杉磯線 Nano 八折後 $23.2/月起，代價是 150ms 左右的延遲
- 重度獨享需求：Forge，記得預算裡加上 $68 一次性安裝費

下單前最後確認三件事：優惠碼在購物車是否生效、年付與月付的差價、以及你那一檔實際包含的 DDoS 防護等級。確認完就可以 👉 [前往 GoMami 選擇對應的香港方案](https://bit.ly/Gomami)，開通後先用 24 小時退款期把跑分、路由和 IO 都驗一遍再決定留下。
