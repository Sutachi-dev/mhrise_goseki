# mhriseの護石判断システム
今回、初めてreadmeを書いたので至らない点等あると思いますが、生暖かい目で見守っていただけると幸いです。
<br />
<br />


## 製作者
***
https://twitter.com/sutachi_agemame
<br />
<br />

## ライセンス
***
個人利用の場合のみ使用許可、改変許可  
個人利用以外の場合は要連絡  
ファイル自体の二次配布不可  
Tesseract-OCRを使用しているため、https://github.com/tesseract-ocr/tesseract
のライセンスに従ってください  
<br />
<br />

## 概要
***
これはMHRiseのお守り画像認識コードのREADMEです  
出力はMHRise スキルシミュ(泣)(https://mhrise.wiki-db.com/sim/)に合わせてあります  
<br />
<br />

## 入力
***
解像度:1920*1080  
拡張子:jpg or mp4  
例1)"./data/test/1.jpg"  
例2)"./data/test/50.mp4"  
<br />
<br />

## 出力
***
スキル1,スキル1レベル,スキル2,スキル2レベル,スロット1数,スロット2数,スロット3数  
例1)業物,2,,0,1,1,1  
例2)弱点特効,2,攻撃,2,0,0,0  
例)"./data/result.csv"  
<br />
<br />

## 実行環境
***
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
	japanese  
	english  
<br />
<br />

## 使い方
***
Tesseract-OCRインストールしてpath通し  
"mhrise.yml"もしくは自力で環境構築  
"main.ipynb"を全セル実行  
入力画像、入力動画を選択(フォルダは不可能、複数ファイル可能)  
"result.csv"に結果が保存される  
テキストファイルで開いてMHRise スキルシミュ(泣)のお守り入力欄に貼り付けてインポート  
<br />
<br />

## ファイル説明
***
data:切り替え検出の比較画像やtestデータを保存するフォルダ  
out_debug:debug用の実際どのくらい判別できているかを確認するフォルダ  
out_image:debug用の判別過程画像を保存するフォルダ  
results:スロット数判別機の学習の最終モデル、学習曲線を保存するフォルダ  
models:スロット数判別機の途中モデル保存フォルダ  
test:スロット数判別機の学習のバリデーションデータ  
train:スロット数判別機の学習のトレーニングデータ  
back:作成中のバックアップフォルダ  

main.ipynb:これだけ実行すればできるファイル  
0or1_test.ipynb:2値化のテストファイル  
classifer_test.ipynb:スロット数判別機のテストファイル  
crop_test.ipynb:座標切り抜きのテストファイル  
mp4_test.ipynb:護石切り替えの検出テストファイル  
tesseract_test.ipynb:OCRのテストファイル  
test.ipynb:リネーム等の適当テストファイル  

error.csv:判別失敗の詳細が保存されるファイル  
result.csv:判別結果が保存されるファイル  
all_skill.xlsx:全スキルが乗っているファイル(この中にないスキルは判別失敗になる)  
mp4_cal:護石切り替えの検出方法検討ファイル  

座標.pptx:切り抜き座標のまとめ  
フローチャート.pptx  
フローチャート.jpg  

mhrise.yml:実行環境  

readme.txt:このファイル  

