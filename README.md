# nmr-qc-project-r
高専生のNMR方式での量子コンピューター制作をレポート形式で記録します。

# [研究開発レポート] 個人開発におけるNMR方式量子コンピューターの自作

## 1. 開発の目的 (Purpose)
- **English Summary:** This project aims to build a personal NMR (Nuclear Magnetic Resonance) quantum computer from scratch. Developed by a 1st-year Japanese KOSEN student to master RF control, magnetic field homogenization, and quantum computing basics.
- **日本語概要:** 将来、量子コンピューターのハードウェア（チップ）開発者になることを目指し、その基礎技術となる「核磁気共鳴（NMR）技術」「高周波（RF）制御」「磁場均一化技術」を実際に手を動かして学ぶため、個人でのNMR量子コンピューター自作に挑戦する。

---

## 2. 理論および原理 (Theory)
NMR方式の量子コンピューターは、原子核の「スピン」を量子ビット（qubit）として利用する。
静磁場 $B_0$ の中に置かれた原子核は、固有の「ラモア周波数（Larmor frequency）$f_0$」で歳差運動を行う。

$$f_0 = \frac{\gamma}{2\pi} B_0$$

ここで $\gamma$ は磁気回転比（Gyromagnetic ratio）である。この状態の原子核に、ラモア周波数に一致する高周波（RF）パルスを印加することで、スピンの状態（量子状態 $|0\rangle$ と $|1\rangle$）を操作し、量子計算を行う。

---

## 3. 設計・開発環境 (Design & Setup)

### 3.1 ハードウェア（予定・検討中）
- **静磁場発生源:** ネオジム磁石（ハルバッハ配列などの検討）
- **高周波送信・受信系:** - **制御マイコン:** Arduino / Raspberry Pi / FPGA など

### 3.2 ソフトウェア
- 開発管理: GitHub
- 制御・データ解析言語: Python (予定)

---

## 4. 開発ログ・進捗 (Development Log)
日々の実験データ、試行錯誤の記録、撮影した写真などはここに時系列で蓄積していく。

💡 **上のメニューの「Outline（目次ボタン）」から各日付にジャンプできます。**

#### 2026年5月20日
- GitHubに本プロジェクトのリポジトリ（開発拠点）を開設。
- ドキュメントを研究レポート形式に刷新。
- 必要となる基本数式（ラモア周波数）の整理。

---

## 5. 課題と次の一手 (Challenges & Next Steps)
- [ ] ターゲットとする原子核（水素原子 $^1\text{H}$ など）の決定と、必要な磁束密度 $B_0$ の計算。
- [ ] 必要となる磁石の選定と、均一な磁場を作るためのシミュレーション方法の調査。
- [ ] 高専の先生にプロジェクトを相談し、アドバイスや実験機材の協力を仰ぐ。

---

## 6. 参考文献・リンク (References)
- (今後参考にした本、WEBサイト、論文のURLをここにメモしていく)
