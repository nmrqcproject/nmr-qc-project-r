# nmr-qc-project-r
高専生のNMR方式での量子コンピューター制作をレポート形式で記録します。

# [研究開発レポート] 個人開発におけるNMR方式量子コンピューターの自作

## 1. 開発の目的 (Purpose)
- **English Summary:** This project aims to build a personal NMR (Nuclear Magnetic Resonance) quantum computer from scratch. Developed by a 1st-year Japanese KOSEN student to master RF control, magnetic field homogenization, and quantum computing basics.
- **日本語概要:** 将来、量子コンピューターのハードウェア（チップ）開発者になることを目指し、その基礎技術となる「核磁気共鳴（NMR）技術」「高周波（RF）制御」「磁場均一化技術」を実際に手を動かして学ぶため、個人でのNMR量子コンピューター自作に挑戦する。

---

## 2. 理論および原理 (Theory)
NMR方式の量子コンピューターは、水の中の水素原子の原子核の「スピン」を量子ビット（qubit）として利用する。

---

## 3. 設計・開発環境 (Design & Setup)

### 3.1 ハードウェア（予定・検討中）
- Tang Nano 20k
- ARDUINO UNO R3

### 3.2 ソフトウェア
- 開発管理: GitHub
- 制御・データ解析言語: Python (予定)

---

## 4. 開発ログ・進捗 (Development Log)
-[PC上での信号制作](#2026-4-24-1)

---

## 5. 課題と次の一手 (Challenges & Next Steps)
- [ ] ターゲットとする原子核（水素原子 $^1\text{H}$ など）の決定と、必要な磁束密度 $B_0$ の計算。
- [ ] 必要となる磁石の選定と、均一な磁場を作るためのシミュレーション方法の調査。
- [ ] 高専の先生にプロジェクトを相談し、アドバイスや実験機材の協力を仰ぐ。

---

## 6. 参考文献・リンク (References)
- (今後参考にした本、WEBサイト、論文のURLをここにメモしていく)




## 開発ログ本文

### 2026-4-24-1
PC上での信号制作

NMR信号:時間と共に弱まっていくサイン波（滑らかで周期的な波形←y=sinx）

$$s(t)=Asin(2\pi ft)e^{-t/T_2}$$

A:振幅
<br>f:NMRの周波数
<br>t:時間
<br>$T_2$:信号が消えるまでの時間定数
<br>e:ネイピア数（何かが滑らかに減る）←原子核の震えが止まっていく様子（FID信号）

```python
#ツール
import numpy as np #数値計算ツール
import matplotlib.pyplot as plt #グラフを描くツール
#定数
fs = 44100 #サンプリング周波数←データ記録の回数(44100Hz=CD)
duration = 1.0 #シミュレーションする時間（s）
f_nmr = 2100.0 #NMRのターゲットの周波数
t2 = 0.5 #信号が消える速さ←減数定数
#メモリ
t = np.linspace(0 , duration , int(fs * duration))#時間軸を作成
#NMR信号
signal = 1.0 * np.sin(2 * np.pi * f_nmr * t) * np.exp(-t/t2) #振幅＊サイン波＊指数減衰
#グラフ化
plt.figure(figsize=(10,4)) #キャンバスの準備(横,縦)
pil.plot(t[:500], signal[:500]) #横軸に時間,縦軸に信号の強さ（最初の500このデーターのみ,44100/500=0.011s）
plt.titl("Ideal NMR Signal 1") #グラフの題名
plt.xlabel("Time[s]")/plt.ylabel("Amplitude") #軸のレベル
plt.grid(True) #グリッドを追加
plt.show() #グラフを表示する
```
<img width="1955" height="888" alt="B17C5046-C540-4362-95D1-E6DAA836B42D_1_201_a" src="https://github.com/user-attachments/assets/51d4e6ab-9047-42e6-b28b-a16d99e0545e" />
