---
title: rack-accept-default から知ったこと
date: 2014-11-07 17:47
tags: rails
---

Garage のコードを読み始めてまず目についたのが

require "rack-accept-default"

[miyagawa/rack-accept-default](https://github.com/miyagawa/rack-accept-default)

これはなんだろうと思うと、

まあ README の内容なんだけれど、

> Rack::AcceptDefault is a tiny piece of middleware that sets default Accept: header when it isn't present, to work around Rails 3.x issues.

> Rails default MIME negotiation (in ActionPack) handles requests without Accept: headers as invalid, and assume it wants the HTML view. This assumption is wrong per RFC 2616 HTTP/1.1 specification.

> If no Accept header field is present, then it is assumed that the client accepts all media types
> Rack::AcceptDefault is a piece of Rack middleware that provides a convenient way to work around this problem, by setting the `*/*` value to the Accept header when it is not present.

[RFC2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) に、

> If no Accept header field is present, then it is assumed that the client accepts all media types

Accept header が渡されない場合、all media types つまり `*/*` とする。とある。

Rails では `*/*` ではなくて html としている。

コードを見ると、Rails 3.x 限定というわけではなく、現在もそうだ。
該当箇所はこの辺。


rails/rails/actionpack/lib/action_dispatch/http

      def formats
        @env["action_dispatch.request.formats"] ||= begin
          params_readable = begin
                              parameters[:format]
                            rescue ActionController::BadRequest
                              false
                            end
          if params_readable
            Array(Mime[parameters[:format]])
          elsif use_accept_header && valid_accept_header
            accepts
          elsif xhr?
            [Mime::JS]
          else
            [Mime::HTML]
          end
        end
      end


