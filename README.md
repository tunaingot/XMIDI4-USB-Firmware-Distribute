# USB-MIDIインターフェース 「XMIDI4 USB」 ファームウェア
ファームウェアのファイルは拡張子が ***mot*** のモトローラSレコードです。\
拡張子前の数字二桁がバージョンを表しており、***10*** が初回リリースです。\
最新のファームウェアは、このページの右側の ***Release*** からダウンロードできます。\
<img width="185" height="352" alt="スクリーンショット 2025-07-31 15 05 01" src="https://github.com/user-attachments/assets/763e9291-8b5d-4b31-a37f-751290c3e2c1" />


# ファームウェアのアップデートに必要なもの
***FAT32でフォーマットしたUSBメモリ***を用意してください。\
USBメモリの中に、このページからダウンロードした拡張子が ***mot*** のファームウェアを入れてください。\
このUSBメモリを使ってファームウェアのアップデートをします。

# ファームウェアのアップデート方法
1. XMIDI4 USBをUSBケーブルでPC、またはACアダプタなどに接続して起動します
2. 本体側面のディップスイッチの ***1*** をONにします
3. ファームウェアの入ったUSBメモリを挿入します
4. 本体側面の上のLEDが点滅し、内蔵フラッシュにプログラムを書き込んでいることを示しています
5. プログラムサイズによっては、1秒ほど点灯または消灯状態で停止することがあります
6. プログラムの書き込みが終了すると、本体側面の下のLEDが点灯します
7. 本体側面のディップスイッチの ***1*** をOFFにします
8. USBメモリを抜きます
9. 通常通りXMIDI4 USBが起動します
<img width="1292" height="289" alt="image" src="https://github.com/user-attachments/assets/02c74b41-4777-4cdd-965b-668b95e0b0e9" />


# ファームウェアのアップデートに失敗した場合
- 手順を間違えても、1からやり直せば再度書き込みができます
- アップデート中に停電などで中断しても、1からやり直せば再度書き込みができます

# 各部の名称と機能
<img width="798" height="673" alt="image" src="https://github.com/user-attachments/assets/867b9090-6202-4c02-9a82-c4911f82a534" />

1. MIDI INインジケータ : MIDI入力があると点滅します
2. MIDI OUTインジケータ : MIDI OUTに出力されると点滅します
3. USB IN/OUTインジケータ : USBの入出力があると点滅します
4. MIDI IN出力先選択 : 入ってきた信号をどのMIDI OUTに出力するかを選択します
5. USBメモリ用コネクタ : ファームウェアのアップデート、設定(後述)の保存・更新でUSBメモリを使用します
6. 動作選択スイッチ : ファームウェアのアップデート、本体動作モード(後述)の選択で使用します
7. 動作インジケータ : ファームウェアのアップデート、USBメモリの動作を表示します
8. MIDI OUTコネクタ : MIDI機器のMIDI INコネクタと接続します
9. MIDI INコネクタ : MIDI機器のMIDI OUTコネクタと接続します
10. PC/ACアダプタ用USBコネクタ : PCまたはACアダプタを接続します

# MIDI信号の流れと動作モード
## スルーモード
<img width="614" height="333" alt="image" src="https://github.com/user-attachments/assets/74d207fe-5a12-487e-ba8c-d712b7ef441e" />

下記のスイッチ設定でスルーモードで動作します。

|⑥動作選択スイッチ|④MIDI IN出力先選択|
| ------------| --------------|
| 1:OFF, 2:OFF|すべてOFF|

MIDI INの出力先は下表のように固定です。\
フィルタ設定、チャンネルマッピング設定はなく、MIDI INに来た信号すべてをそのままMIDI OUTに出力します。\
USBの入出力は行われ、MIDI OUTはMIDI INとUSBをミキシング処理して出力されます。

|MIDI IN|MIDI OUT出力先|
| ------------| --------------|
| 1|1|
| 2|2|
| 3|3|
| 4|4|

## スイッチルーティングモード
<img width="614" height="366" alt="image" src="https://github.com/user-attachments/assets/f2f17b8e-b4fb-43f6-86b0-4a624edd1af3" />

下記のスイッチ設定でスイッチルーティングモードで動作します。

|⑥動作選択スイッチ|④MIDI IN出力先選択|
| ------------| --------------|
| 1:OFF, 2:OFF|いずれかがON|

MIDI INの出力先は④MIDI IN出力先選択のスイッチで選択したMIDI OUTに出力されます。\
フィルタ設定、チャンネルマッピング設定はなく、MIDI INに来た信号全てをそのまま選択したMIDI OUTに出力します。\
USBの入出力は行われ、MIDI OUTはMIDI INとUSBをミキシング処理して出力されます。

異なるMIDI INで同じMIDI OUTを選択した場合、ミキシング処理してMIDI OUTに出力します。\
出力先選択スイッチが全てOFFの場合、そのMIDI INに入ってきた信号はUSBだけに送られます。

## プログラムモード
<img width="614" height="588" alt="image" src="https://github.com/user-attachments/assets/bca6a041-0e9e-428a-a3c7-4864aa2c6db4" />

下記のスイッチ設定でプログラムモードで動作します。

|⑥動作選択スイッチ|④MIDI IN出力先選択|
| ------------| --------------|
| 1:OFF, 2:ON|無関係|

内蔵ストレージに保存されているMIDI INの出力先設定、フィルタ設定、チャンネルマッピング設定等、全てが適用されます。

### パッチ(設定)の編集アプリ
プログラムモードの設定編集は、専用のアプリ[XMIDI USB Editor](https://github.com/tunaingot/XMIDI-USB-Editor-Distribute)で行います。\
macOS専用で、GitHubで公開しています。

### パッチについて
パッチは本体内に32持つことができます。\
電源投入時はパッチ番号1が選択されています。\
パッチの選択は

- バンクセレクトを併用したプログラムチェンジ
- コントロールチェンジ

のいずれか、または両方で行うことができます。\
バンクセレクトの番号、コントロールチェンジの番号も専用のアプリで変更することができます。

パッチの選択はどのMIDI INからでも可能です。\
そのため、接続しているMIDI機器で使用していないバンクセレクト、コントロールチェンジを選んでください。\
また、パッチを選択するプログラムチェンジ、バンクセレクト、コントロールチェンジはMIDI OUT、およびUSBには送信されません。

### 本体内でのパッチデータの扱い
<img width="607" height="264" alt="image" src="https://github.com/user-attachments/assets/6016ef16-da52-4a2d-bcc8-baac6dd16b48" />

パッチデータは電源を切っても消えない内蔵ストレージに保存されています。\
電源投入後、内蔵ストレージからメモリーに読み出されます。\
さらに選択されたパッチをテンポラリに読み出し、フィルタなどの演算やパッチ編集で利用します。

### パッチデータの取り出し
32個のパッチは「**CCMRAM.XMB**」というファイルをUSBメモリを使って取り出すことができます。\
ファイルが入っていないUSBメモリを挿入すると、**CCMRAM.XMB**がUSBメモリの中にコピーされます。

### 取り出したパッチデータの扱い
専用アプリを使って、本体へ転送することができます。\
また、XMBファイルをUSBメモリに入れて本体に挿入すると、本体のメモリーへ転送されます。\
ファイル名は半角英数8文字まで認識します。\
主に

1. MacユーザーにCCMRAM.XMBファイルを渡す
2. これを元にデータを編集してもらう
3. 編集したXMBファイルを受け取る
4. 受け取ったXMBファイルをUSBメモリに入れて本体に挿入
5. メモリーに転送後、内蔵ストレージに自動保存

というMacを所有していない方向けに用意した機能ですが、あまり実用的なものではありませんので、Macの導入をご検討ください。

## フィルタ機能
### CH Message
ON / OFFの設定がCH個別に指定可能です。

|  | Message |
| ---- | ------- |
|8x|Note Off|
|9x|Note On|
|Ax|Poly Key Pressure|
|Bx|Control Change|
|Cx|Program Change|
|Dx|CH Pressure|
|Ex|Pitch Bend|

Note OffをフィルタでOFFにすると、音が鳴り止まなくなりますのでご注意ください。\
現実的な設定項目ではありませんが、データ処理の関係で設けてあります。

### Mode Message
ON / OFFの設定がCH個別に指定可能です。

|  | Message |
| ---- | ------- |
|120|All Sound Off|
|121|Reset All Controller|
|122|Local Control|
|123|All Note Off|
|124|Omni Off|
|125|Omni On|
|126|Mono Mode On|
|127|Poly Mode On|

### System Message
ON / OFFの設定がメッセージ毎に指定可能です。

|  | Message | | Message |
| ---- | ------- | ---- | -----|
|F0|Start of SYSEX|F8|Timing Clock|
|F1|MIDI Time Code|F9|Start|
|F2|Song Position|FA|Continue|
|F3|Song Select|FB|Stop|
|F4||FC||
|F5||FD||
|F6|Tune Request|FE|Active Sensing|
|F7|End of SYSEX|FF|System Reset|

F7が個別にON / OFFできるようになっていますが、内部処理ではF0と連動しています。\
データ処理の関係で設けてあります。

### Control Change
よく利用されるコントロール・チェンジのON / OFF設定がCH個別に指定可能です。

| Message | CC# | Message | CC# | Message | CC# |
| ------- | --- | ------- | --- | ------- | --- |
|Modulation|1|Cut Off|74|Envelope Release|72|
|Volume|7|Resonance|71|Chorus|93|
|Expression|11|Vibrato Rate|76|Reverb|91|
|Pan Pot|10|Vibrato Depath|77|||
|Hold Pedal|64|Vibrato Delay|78|||
|Sostenuto Pedal|66|Portamento Time|5|||
|Soft Pedal|67|Envelope Attack|73|||
|Bank Select|0/32|Envelope Decay|75|||

### Special Bit
特殊なデータのフィルタとして用意してあります。

|bit|Function|
|---|--------|
|0|SC-88ディスプレイデータ|

### Key Range
CH毎にキーレンジ、オクターブが指定可能です。\
MIDIインターフェース側でスプリット演奏を実現することを想定したものです。

## チャンネル・マッピング機能
CHを入れ替える機能です。\
さらにCHを入れ替えるだけでなく、1つの入力CHに対して複数のCHを指定して出力することも可能です。\
1つのMIDIチャンネルで、多チャンネルのスプリット演奏を実現するときなどに利用します。

## ルーティング機能
MIDI INをどのMIDI OUTへ出力するかをCH毎に設定可能です。\
MIDI OUTを複数指定することも可能です。\
システム・メッセージ、SC-88ディスプレイデータを個別にルーティング、ミュートすることが可能です。\


