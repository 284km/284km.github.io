---
title: Java で input type="file" アップロード
date: 2013-08-16 10:26
tags: java
---

`input type="file"` のファイルをアップロードする時、java だと org.apache.commons.fileupload.servlet.ServletFileUpload とか使うと思います。

以下の具合に、 getName() の取得結果が IE だけ違ったので少し悲しくなりました。

- chrome, firefox はファイル名だけ取得
- IE はフルパス取得

> <input type="file" id="files" name="files">

    ServletFileUpload upload = new ServletFileUpload(factory);
    upload.setSizeMax(-1);
    List<?> items = upload.parseRequest(request);
    for (Object val : items) {
      FileItem item = (FileItem) val;
    
      // IE だけフルパスで取れるんだけど、、、
      // chrome, firefox はファイル名のみ
      String fileName = item.getName();
    
      if (!item.isFormField()) {
        if ((fileName != null) && (!fileName.equals(""))) {
    
          // IE の場合 ファイル名だけ抜き出すなど
          Integer ie = fileName.lastIndexOf("\\");
          if (ie > 0) {
            fileName = fileName.substring(ie);
          }
    
          item.write(new File(upDir + "/" + fileName));
        }
      }
    }

