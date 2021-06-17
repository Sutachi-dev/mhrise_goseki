# mhriseの護石判断システム
今回、初めてreadmeを書いたので至らない点等あると思いますが、生暖かい目で見守っていただけると幸いです。
<br />
<br />


## 製作者
https://twitter.com/sutachi_agemame
<br />
<br />

## ライセンス
個人利用の場合のみ使用許可、改変許可  
個人利用以外の場合は要連絡  
ファイル自体の二次配布不可  
Tesseract-OCRを使用しているため、https://github.com/tesseract-ocr/tesseract
のライセンスに従ってください  
<br />
<br />

## 概要
これはMHRiseのお守り画像認識コードのREADMEです  
出力はMHRise スキルシミュ(泣)(https://mhrise.wiki-db.com/sim/
)に合わせてあります  
<br />
<br />

## 入力
解像度:1920*1080  
拡張子:jpg or mp4  
例1)"./data/test/1.jpg"  

![1](https://user-images.githubusercontent.com/52289901/122439107-502cdb00-cfd6-11eb-8871-03f68f1d3407.jpg)

例2)"./data/test/50.mp4"  
![50_Trim_2](https://user-images.githubusercontent.com/52289901/122443526-a734af00-cfda-11eb-9402-535279d8d230.gif)


<br />
<br />

## 出力
スキル1,スキル1レベル,スキル2,スキル2レベル,スロット1数,スロット2数,スロット3数  
例1)業物,2,,0,1,1,1  
例2)弱点特効,2,攻撃,2,0,0,0  
例)"./data/result.csv"  

excelで開いた場合
![result csv - Excel 2021_06_18 1_50_59](https://user-images.githubusercontent.com/52289901/122441610-a9960980-cfd8-11eb-94c8-54bc885ece2b.png)

メモ帳で開いた場合  
![result csv - メモ帳 2021_06_18 1_56_57](https://user-images.githubusercontent.com/52289901/122441649-b4509e80-cfd8-11eb-8eb5-be8394ea97da.png)
<br />
<br />

## 実行環境
windows10Home  
AMD Ryzen7 5800X  
Nvidia Geforce RTX2070  
gpuドライバーver:27.21.14.6663  
python:3.7.10  
cuda:10.1  
cudnn:7.6.5  
cudatoolkit:10.1.243  
tensorflow:2.3.0  
Tesseract-OCRv5.0.0-alpha.20210506  
- japanese  
- english  
<br />
<br />

## 使い方
1. Tesseract-OCRインストールしてpath通し  
2. "pip install -r requirements.txt"もしくは"conda env create -n mhrise -f mhrise.yml"もしくは自力で環境構築  
3. "main.ipynb"を全セル実行  
4. 入力画像、入力動画を選択(フォルダは不可能、複数ファイル可能)  
5. "result.csv"に結果が保存される  
6. テキストファイルで開いてMHRise スキルシミュ(泣)のお守り入力欄に貼り付けてインポート  
<br />
<br />

## ファイル説明
data:切り替え検出の比較画像やtestデータを保存するフォルダ  
main.ipynb:これだけ実行すればできるファイル  
all_skill.xlsx:全スキルが乗っているファイル(この中にないスキルは判別失敗になる)  
mhrise.yml:実行環境  
README.md:このファイル  

## 備考
Tesseract-OCRは、"C:\Program Files\Tesseract-OCR\tesseract.exe"のように配置すること  
今後のアップデート予定
- path入力ではなくimage入力にすることで高速化
- フルHD以外への対応
- 手撮り等のゲームキャプチャ以外の入力への対応
- webアプリ化