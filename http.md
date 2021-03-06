## http request

#### 请求行 request-head

- 方法：get、put等
- URL：资源的URL
- 协议的版本：http1.1

#### 请求头 headers

- host：请求的域名地址
- User-Agent：记录客户端浏览器的详细信息，用于判断访问的客户端是否合法（爬虫）
- Accept：
- Accept Language：语言及比重
- Accept-Encoding：压缩内容的编码方式（不是字符的编码方式）如用gzip压缩编码方式，还是哈夫曼压缩编码方式（deflate）
- Accept-Charset：字符编码格式
- Content-Type：
- Content-Length：内容的长度
- Connection：是否需要持久连接（Keep-Alive，close）
- Keep-Alive：表示连接持续时长：Keep-Alive：300
- Cookie：http是无状态的，cookie用于保存状态信息，如用户登录信息。
- Refer：
- Pragma：
- Cache-Control：

#### 空行

#### 请求内容





## http request

对get和post请求的相应

前两行为状态行，包括服务器的http版本和响应码。

#### 响应代码：

- 1开头：表示收到请求，继续进程
  - 100  （继续）请求者应当继续提出请求。服务器返回此代码表示已收到请求的第一部分，正在等待其余部分。 
  - 101  （切换协议）请求者已要求服务器切换协议，服务器已确认并准备切换。
- 2开头：表示请求成功，发送get后返回
  - 200   （成功）  服务器已成功处理了请求。通常，这表示服务器提供了请求的网页。
  - 201   （已创建）  请求成功并且服务器创建了新的资源。
  - 202   （已接受）  服务器已接受请求，但尚未处理。
  - 203   （非授权信息）  服务器已成功处理了请求，但返回的信息可能来自另一来源。
  - 204   （无内容）  服务器成功处理了请求，但没有返回任何内容。
  - 205   （重置内容）服务器成功处理了请求，但没有返回任何内容。
  - 206   （部分内容）  服务器成功处理了部分 GET 请求。
- 3开头：表示重发重定位，为了完成操作必须进一步动作
  - 300   （多种选择）  针对请求，服务器可执行多种操作。服务器可根据请求者 (user agent) 选择一项操作，或提供操作列表供请求者选择。
  - 301   （永久移动）  请求的网页已永久移动到新位置。服务器返回此响应（对 GET 或 HEAD 请求的响应）时，会自动将请求者转到新位置。
  - 302   （临时移动）  服务器目前从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求。
  - 303   （查看其他位置）请求者应当对不同的位置使用单独的 GET 请求来检索响应时，服务器返回此代码。
  - 304   （未修改）自从上次请求后，请求的网页未修改过。服务器返回此响应时，不会返回网页内容。
  - 305   （使用代理）请求者只能使用代理访问请求的网页。如果服务器返回此响应，还表示请求者应使用代理。
  - 307   （临时重定向）  服务器目前从不同位置的网页响应请求，但请求者应继续使用原有位置来进行以后的请求。
- 4开头：表示客户端错误
  - 400   （错误请求）服务器不理解请求的语法。
  - 401   （未授权）请求要求身份验证。对于需要登录的网页，服务器可能返回此响应。
  - 403   （禁止）服务器拒绝请求。
  - 404   （未找到）服务器找不到请求的网页。
  - 405   （方法禁用）禁用请求中指定的方法。
  - 406   （不接受）无法使用请求的内容特性响应请求的网页。
  - 407   （需要代理授权）此状态代码与 401（未授权）类似，但指定请求者应当授权使用代理。
  - 408   （请求超时）  服务器等候请求时发生超时。
  - 409   （冲突）  服务器在完成请求时发生冲突。服务器必须在响应中包含有关冲突的信息。
  - 410   （已删除）  如果请求的资源已永久删除，服务器就会返回此响应。
  - 411   （需要有效长度）服务器不接受不含有效内容长度标头字段的请求。
  - 412   （未满足前提条件）服务器未满足请求者在请求中设置的其中一个前提条件。
  - 413   （请求实体过大）服务器无法处理请求，因为请求实体过大，超出服务器的处理能力。
  - 414   （请求的 URI 过长）请求的 URI（通常为网址）过长，服务器无法处理。
  - 415   （不支持的媒体类型）请求的格式不受请求页面的支持。
  - 416   （请求范围不符合要求）如果页面无法提供请求的范围，则服务器会返回此状态代码。
  - 417   （未满足期望值）服务器未满足"期望"请求标头字段的要求。
- 5开头：表示服务器错误
  - 500   （服务器内部错误）  服务器遇到错误，无法完成请求。
  - 501   （尚未实施）服务器不具备完成请求的功能。例如，服务器无法识别请求方法时可能会返回此代码。
  - 502   （错误网关）服务器作为网关或代理，从上游服务器收到无效响应。
  - 503   （服务不可用）服务器目前无法使用（由于超载或停机维护）。通常，这只是暂时状态。
  - 504   （网关超时）  服务器作为网关或代理，但是没有及时从上游服务器收到请求。
  - 505   （HTTP 版本不受支持）服务器不支持请求中所用的 HTTP 协议版本。 

#### 响应头


          1). Server ：该响应头是服务器告诉浏览器，当前响应的服务类型和版本。
          2). Content-Type响应头：服务器告诉浏览器响应内容是什么类型，以及采用的是什么字符编码。该响应头的值现在为：text/html;charset=utf-8。说明响应信息的类型是文本类型中的html，使用的字符编码是utf-8。
          3). Content-Length响应头：服务器告诉浏览器，Content-Length响应头表明了响应实体的大小，该响应内容的长度现在是312个字节。
          4). Date响应头：表示是服务器是在什么时候响应回浏览器，注意这里的时间是按照美国时间来计算。
          5). Accept-Ranges: bytes - 该响应头表明服务器支持Range请求,以及服务器所支持的单位是字节(这也是唯一可用的单位).我们还能知道:服务器支持断点续传,以及支持同时下载文件的多个部分,也就是说下载工具可以利用范围请求加速下载该文件.Accept-Ranges: none 响应头表示服务器不支持范围请求.
          6). Last-Modified：服务器上文件的最后修改时间


## Cookie

tcp三次握手之后，然后客户端发出一个http request不包含信息，服务器response返回一个报文，其中有set-cookie段，客户端会将这些信息填充到请求的cookie中。通过认证程序后，服务器会将cdb_auth写入cookie中返回，这时候客户端就可以使用cookie了

#### cookie和session

cookie：

- 加密后破解可能性小
- cookie中不存放敏感数据被窃取了也没问题
- cookie生命周期，让窃取者偷到过期的cookie
- cookie有数量和长度限制，每个domain最多20条cookie，cookie长度不超过4KB
- 即使cookie加密，盗用者只需要原封不动地发回去。
- 有些状态不能保存在客户端，比如用一个计数器防止重复提交，或者计算提交次数。

cookie字段：

- name
- value
- domain：说明cookie对于哪个域是有效的，指明了哪些主机可以接受cookie，不指定默认为当前文档的主机：不包含子域名，如果指定了一般就包含子域名。设置 Domain=mozilla.org，则 Cookie 也包含在子域名中（如 developer.mozilla.org）。
- path：表明cookie影响到的路径，哪些路径可以接受cookie
- expire：max-age：失效时间
- httpOnly：告知浏览器不允许通过脚本
- secure：安全标志，只有ssl链接才能使用

session：

- 安全性更高，因为信息保存在服务器上
- session对服务器会造成较大的压力。
- session可以保存各种类型的信息，而cookie只能保存ascii码





## http与https

https通过ssl进行加密，防止数据传输的不安全。

公钥私钥。

客户端发送请求，服务器传回一个加密公钥。客户端产生于一个会话密钥，并用服务器的公钥加密发回给服务器。服务器端用私钥进行解析，之后用会话密钥进行通信。





## http方法

GET：请求资源（幂等）

HEAD：获取报文首部，主要用于确认URL的有效性。

POST：主要用来传输数据（不幂等）

PUT：上传文件，一般不用此方法（幂等，多次替换只是用同一个文件替换，最终的结果是相同的）

PATCH：用于修改资源。PUT也用于修改资源，不过是整个资源替换，而patch是部分修改（非幂等）

DELETE：删除文件（幂等）

OPTIONS：查询指定URL

CONNECT：用SSL和TSL协议把通信内容加密。

TRACE：追踪路径。





## http缓存

