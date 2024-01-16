---
layout: default
title: グループウェアの新しいテナントの作成方法
---

## 新しいテナントの作成手順

1. システム管理者でシラサギにログインし、システム設定 - グループとメニューをたどり、新しいグループを作成する。
2. 同じく、システム管理者でシラサギにログインし、システム設定 - ユーザーとメニューをたどり、1で作成したグループの管理ユーザーを新規作成するか、既存のユーザーを編集し、「グループ」に1で作成したグループを追加する。
3. Rake Task "gws:set_admin_role" を実行し、2で作成した管理ユーザーを1で作成したグループの管理者として設定する。
  ~~~
  $ bundle exec rake gws:set_admin_role user=管理ユーザーID site=新しいグループ名
  ~~~
4. 2 で作成した管理ユーザーでシラサギにログインしなおし、1のグループにアクセスし、設定していく。