---
title: [Esc, C-[, C-C 対応版] Terminal Vimで Insert モードを抜ける時に英数入力に切り替える方法
date: 2013-12-03 20:11
tags: vim
---

Mac の場合です。

### 解決方法

KeyRemap4MacBook を使えば可能。

- ESC と Ctrl+C と Ctrl+[ に対応させる設定

private.xml

    <?xml version="1.0"?>
    <root>
      <list>
        <item>
          <name>LeaveInsMode with EISUU(Terminal)</name>
          <identifier>private.app_terminal_esc_with_eisuu</identifier>
          <only>TERMINAL</only>
          <autogen>--KeyToKey-- KeyCode::ESCAPE, KeyCode::ESCAPE, KeyCode::JIS_EISUU</autogen>
          <autogen>--KeyToKey-- KeyCode::BRACKET_LEFT, VK_CONTROL, KeyCode::BRACKET_LEFT, VK_CONTROL, KeyCode::JIS_EISUU</autogen>
          <autogen>--KeyToKey-- KeyCode::C, VK_CONTROL, KeyCode::C, VK_CONTROL, KeyCode::JIS_EISUU</autogen>
        </item>
      </list>
    </root>

あとは ReloadXML して checkbox ON して有効にましょう。そしたらOK。
