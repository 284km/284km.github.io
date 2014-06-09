---
title: iOS UIViewController lifecycle
date: 2014-06-09 11:20
tags: ios
---

### UIViewController のライフサイクルについて

http://blog.77jp.net/iphone%E9%96%8B%E7%99%BA-uiviewcontroller-%E3%83%A9%E3%82%A4%E3%83%95%E3%82%B5%E3%82%A4%E3%82%AF%E3%83%AB-viewdidload-viewwillappear-viewdidappear-viewwilldisappear-viewdiddisappear-ios-%E9%80%86
http://blog.livedoor.jp/sasata299/archives/52029262.html

> アプリがバックグラウンドへ移動した場合や、他のアプリ、
> 他の機能にて当Viewがメモリから削除された場合は、再度 viewDidLoad が実行されます。

> init(インスタンス作成時に呼び出したイニシャライザ)
> 　　↓
> viewDidLoad
> 　・View が初めて呼び出される時に1回だけ呼ばれます。
> 　・アプリ起動後に初めて当Viewが表示された場合に1度だけ呼ばれます。
> 　　↓
> viewWillAppear
> 　・View が表示される直前に呼ばれるメソッド
> 　・タブ等の切り替え等により、画面に表示されるたびに呼び出されます。
> 　・タブが切り替わるたびに何度でも呼ばれます。
> 　　↓
> viewDidAppear
> 　・View の表示が完了後に呼び出されるメッソド
> 　・タブ等の切り替え等により、画面に表示されるたびに呼び出されます。
> 　・タブが切り替わるたびに何度でも呼ばれます。
> 　　↓
> viewWillDisappear
> 　・View が他のView (画面から消える) 直前に呼び出されるメッソド
> 　・View が他のView (画面から消える) 直前に呼び出されるメッソド
> 　・タブが切り替わるたびに何度でも呼ばれます。
> 　　↓
> viewDidDisappear
> 　・View が他のView (画面から消えた) 非表示後に呼び出されるメッソド
> 　・View が他のView (画面から消える) 直前に呼び出されるメッソド
> 　・タブが切り替わるたびに何度でも呼ばれます。

---

起動したとき

- ViewController viewDidLoad
- ViewController viewWillAppear
- ViewController viewDidAppear


Nextボタンをタップして遷移したとき

- NextViewController viewDidLoad
- ViewController viewWillDisappear
- NextViewController viewWillAppear
- ViewController viewDidDisappear
- NextViewController viewDidAppear


戻ったとき

- NextViewController viewWillDisappear
- ViewController viewWillAppear
- NextViewController viewDidDisappear
- ViewController viewDidAppear

