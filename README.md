file_lib
======================
ファイル操作に関連するクラス、関数を作成しました
ご利用は自己責任でご自由にどうぞ

使い方
------
１．pipコマンドを実行し、モジュールをダウンロードしてください

    pip install file_lib

２．クラスをインポートし、下記例の用に使用してください

    from file_lib.csv_file import CsvFileReader
    reader = CsvFileReader(/tmp/item_list.csv)
    for line in reader.read_file()
        print ','.join(line)

    from file_lib.file_utils import get_file_lines
    for line in get_file_lines(/tmp/item_list.csv)
        print line

機能紹介
------
### CsvFileReader
#### CSVファイル読込機能を保持したクラスです、マルチバイト文字にも対応しています。
***
__init__(file_path, encode='utf-8', quote='"', delimiter=',', line_feed='\r\n', skip_initial_space=False):

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 読み込みたいCSVのファイルパス | - |
| encode | × | 文字コード | utf-8 |
| quote | × | くくり文字 | " |
| delimiter | × | 区切り文字 | , |
| line_feed | × | 改行文字 | \r\n |
| skip_initial_space | × | カラム間の空白有無 | False |
***
read_file():CSVファイルを読み込みます。

戻り値：List(yield)
***

### CsvFileWriter
#### CSVファイル作成機能を保持したクラスです、マルチバイト文字にも対応しています。
***
__init__(file_path, encode='utf-8', quote='"', delimiter=',', line_feed='\r\n', skip_initial_space=False):

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 作成したいCSVのファイルパス | - |
| encode | × | 文字コード | utf-8 |
| quote | × | くくり文字 | " |
| delimiter | × | 区切り文字 | , |
| line_feed | × | 改行文字 | \r\n |
| skip_initial_space | × | カラム間の空白有無 | False |
***
write_file(fetch_data):CSVファイルを複数行書き込みます、書き込み終了後、自動でファイルをクローズします

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| fetch_data | ◯ | 書き込みたい内容、リストのリストを指定する | - |
戻り値：なし
***
write_one_line(data):CSVファイルを１行書き込みます

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| data | ◯ | 書き込みたい内容、リストを指定する | - |
戻り値：なし
***
close():CSVファイルをクローズします

戻り値：なし
***

### その他ユーティリティ
#### ディクショナリ
***
merge_dict(origin_dict, add_dict):ディクショナリにディクショナリをマージします、dict.updateと違い、ディクショナリの中に該当するキーが存在しない場合も保持したままとなります

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| origin_dict | ◯ | マージ元となるディクショナリ | - | 
| add_dict | ◯ | マージ対象のディクショナリ | - | 
戻り値：マージしたディクショナリ(dict)
***
replace_param_to_arg_dict(original_data, arg_dict):ディクショナリ無いの「${」「}」で囲まれた値を置換します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| origin_dict | ◯ | マージ元となるディクショナリ | - | 
| add_dict | ◯ | 置換情報 | - | 
戻り値：なし
***

#### ファイル
***
append_file(base_file_path, append_file_path):ファイルにファイルの内容を追記します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| base_file_path | ◯ | 追記先のファイル | - | 
| append_file_path | ◯ | 追記情報ファイル | - | 
戻り値：なし
***
get_file_lines(file_path):ファイルの内容を取得します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 内容を取得したいファイルパス | - | 
戻り値：List
***
get_file_line_cnt(file_path):ファイルの行数を取得します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 行数を取得したいファイルパス | - | 
戻り値：ファイル行数(int)
***
grep_file(file_path, grep_str_list, output_file_path, file_code='utf-8', output_path='utf-8'):ファイルのグレップ結果を抽出します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | grepするファイルパス | - | 
| grep_str_list | ◯ | grepする文字列、配列で複数指定できる | - |
| output_file_path | ◯ | grep結果を吐き出すファイルパス | - |
| file_code | × | grepするファイルの文字コード | utf-8 |
| output_path | × | grep結果を吐き出すファイルの文字コード | utf-8 |
戻り値：なし
***
get_file_timestamp(file_path):ファイルのタイムスタンプを取得します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | タイムスタンプを取得したいファイルパス | - | 
戻り値：タイムスタンプ(datetime)
***
replace_file_contents(from_file_path, to_file_path, replace_dict):ファイルの中身を置換します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| from_file_path | ◯ | 置換したいファイルのパス | - |
| to_file_path | ◯ | 置換結果を出力するファイルのパス | - |
| replace_dict | ◯ | 置換情報 | - |
戻り値：なし
***
get_dir_list(target_dir, include_hidden_folder=False):指定したディレクトリ内に存在するディレクtリのリストを取得します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_dir | ◯ | 対象ディレクトリのパス | - |
| include_hidden_folder | × | 隠しフォルダを含めるか否か。含める場合はTrueを設定 | False |
戻り値：ディレクトリ名称(List)
***
get_file_path_list(target_folder_path, asc=True):指定したディレクトリ内に存在するファイルのパスリストを取得します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | ◯ | 対象ディレクトリのパス | - |
| asc | × | ファイルのタイムスタンプが降順の状態で取得したい場合はFalseを設定 | True |
戻り値：ディレクトリパス(List)
***
make_dirs(dir_path):安全にディレクトリを作成します

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| dir_path | ◯ | 作成したいディレクトリのパス | - |
戻り値：なし
***
interval_delete(target_folder_path, file_count):指定したディレクトリ内に存在するファイルを指定した数だけ残して削除する、新しいファイルを優先して残す

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | ◯ | 対象ディレクトリのパス | - |
| file_count | ◯ | 残しておきたいファイル数 | - |
戻り値：なし
***
interval_delete_folder(target_folder_path, leave_count):指定したディレクトリ内に存在するディレクトリを指定した数だけ残して削除する、新しいディレクトリを優先して残す

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_folder_path | ◯ | 対象ディレクトリのパス | - |
| leave_count | ◯ | 残しておきたいディレクトリ数 | - |
戻り値：なし
***
backup_file(file_path, target_dir):指定したディレクトリにファイルをコピーする、コピーしたファイルは自動的にファイル名に時間情報が付与される

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | バックアップしたいファイルパス | - |
| target_dir | ◯ | バックアップするディレクトリ | - |
戻り値：なし
***

#### gzip
***
compress_gzip(file_path, output_file_path=None):gzipファイルに圧縮する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 圧縮したいファイルのパス | - | 
| output_file_path | × | 圧縮後のファイルパス、未指定の場合はfile_path+.gzというファイルパスになる | None | 
戻り値：なし
***
un_gzip(file_path, output_file_path):gzipファイルを回答する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 解答したいファイルのパス | - | 
| output_file_path | ◯ | 解答後のファイルパス | - | 
戻り値：なし
***
is_gzip(file_path):gzipファイルかどうか判定する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 確認したいファイルのパス | - | 
戻り値：なし
***

#### json
***
read_json_file(file_path, encoding='utf-8'):jsonファイルを読み取り、jsonオブジェクトを取得する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | 読み取りたいjsonファイルのパス | - | 
| encoding | × | ファイルの文字コード | utf-8 | 
戻り値：jsonオブジェクト(Dict)
***
write_json_file(file_path, data, encoding='utf-8'):jsonオブジェクトをファイルに落とし込みます

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| file_path | ◯ | オブジェクトを保存したいファイルのパス | - |
| data | ◯ | 保存したいjsonオブジェクト | - |
| encoding | × | ファイルの文字コード | utf-8 | 
戻り値：なし
***

#### 文字列
***
replace_str_by_dict_value(target_str, replace_dict):対象の文字列を指定したディクショナリ情報を元に置換する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | ◯ | 置換したい文字列 | - |
| replace_dict | ◯ | 置換情報 | - |
戻り値：置換後の文字列
***
get_string_width(target_str):文字数を数える、マルチバイトは2と換算する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | ◯ | 対象文字列 | - |
戻り値：文字数(int)
***
cut_string(target_str, length):文字列をカットする、マルチバイト文字をまたいだ場合は除外される

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | ◯ | 対象文字列 | - |
| length | ◯ | カットしたい文字数 | - |
戻り値：カットした文字
***
to_camel_string(target):スネークケースをキャメルケースに変換する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target_str | ◯ | 対象文字列 | - |
戻り値：キャメルケース文字列
***
convert_str(target):オブジェクトを文字列に変換する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| target | ◯ | 対象オブジェクト | - |
戻り値：変換した文字列
***

#### zip
***
compress(compress_file_path, target_dir):指定したディレクトリをzipファイルに圧縮する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | ◯ | 圧縮ファイルのパス | - |
| target_dir | ◯ | 圧縮したいディレクトリのパス | - |
戻り値：圧縮ファイルのパス
***
compress_files(compress_file_path, target_file_path_list):指定した複数のファイルをzipファイルに圧縮する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | ◯ | 圧縮ファイルのパス | - |
| target_file_path_list | ◯ | 圧縮したい複数のファイルパス | - |
戻り値：圧縮ファイルのパス
***
decompress(decompress_file_path, target_dir):zipファイルを解凍する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| decompress_file_path | ◯ | 圧縮ファイルのパス | - |
| target_dir | ◯ | 解凍したいディレクトリのパス | - |
戻り値：解凍されたファイルのパス(List)
***
compress_file(compress_file_path, target_file_path):ファイルをzipファイルに圧縮する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| compress_file_path | ◯ | 圧縮ファイルのパス | - |
| target_file_path | ◯ | 圧縮したいファイルのパス | - |
戻り値：圧縮ファイルのパス
***
compress_file_password(move_dir, compress_file_name, target_file_name, password):暗号化されたzipファイルを作成する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| move_dir | ◯ | 圧縮ファイルの配置ディレクトリ | - |
| compress_file_path | ◯ | 圧縮ファイルの名称 | - |
| target_file_path | ◯ | 圧縮したいファイルのパス | - |
| password | ◯ | パスワード | - |
戻り値：なし
***
decompress_file(decompress_file_path, target_dir, target_file):圧縮されたzipファイルのなかから、特定のファイルのみを解凍する

| 名前 | 必須 | 説明 | デフォルト値 | 
|:-----------|:------------:|:-----------|:-----------| 
| decompress_file_path | ◯ | 解凍したいファイルのパス | - |
| target_dir | ◯ | 解凍したファイルを配置するディレクトリ | - |
| target_file | ◯ | 解凍したいファイルの名前| - |
戻り値：解凍したファイルのパス
***

関連情報
--------
1. [ググレカス(ブログ)](http://gugurekasu.blogspot.jp/)
2. [LinkedIn](https://jp.linkedin.com/in/akirataniguchi1)
 
ライセンス
----------
Distributed under the [MIT License][mit].
[MIT]: http://www.opensource.org/licenses/mit-license.php
