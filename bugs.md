# 現在のバグまとめ

バグ追跡

## admin権限のチェックに問題(報告者:鈍牛 nZmkde79JNN)
- 問題点
    - 二つ以上のIPアドレスをOR指定できない。
    - IPアドレスの範囲指定ができない
- 状況
    - 正規表現のチェックに問題ありか？

## スパム投稿なのに、スレ一覧でスレが上がる(報告者:名無しさん)
- 問題点
- 状況
    - 誤って時刻情報を更新していないかチェックしている。
