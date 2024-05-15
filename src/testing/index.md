# 测试

```
安全测试
    密码安全性问题
        在软件测试过程中，安全性问题是一个非常重要的方面，因为它关乎到系统和用户的信息安全。测试中使用的数据可能包含敏感信息，如个人身份信息、信用卡号码等。在测试过程中，必须确保这些敏感数据得到妥善处理，不会被泄露或滥用。在测试过程中，我们重点对登录功能安全性进行了处理。其中，测试人员需要验证系统在存储用户密码时是否采用安全的加密算法，如哈希函数，并是否使用适当的加盐机制。加盐可以防止彩虹表攻击，提高密码的安全性。而在确保在用户登录时，密码通过加密的传输层协议（如TLS或SSL）进行传输。这有助于防止中间人攻击，确保用户输入的密码在传输过程中不被窃取或篡改。我们还在系统中实施了强密码策略，包括密码长度、复杂性要求、定期密码更改等。测试应覆盖各种密码输入情境，确保系统正确地执行密码策略同时，由于系统支持多因素身份验证，测试其安全性。确保第二因素的传输和存储也是安全的，并测试在多因素身份验证场景下系统的整体安全性。在核查宝系统中，我们支持领导和普通管理员两种身份，因此测试这两种身份的整体安全性是十分重要的。最后，输入密码多次尝试失败后封禁账号是一种常见的安全策略，旨在防范恶意攻击者通过暴力破解密码的方式尝试入侵用户账户。这种策略有助于提高账户的安全性，但同时需要谨慎设计，以免影响正常用户的体验。
    验证码安全性问题
        验证码在安全性方面起到了重要的作用，主要用于验证用户身份、防止自动化攻击和确保用户与系统的交互安全。然而，在设计和使用验证码时，仍然可能面临一些安全性问题。恶意攻击者可能使用自动化工具，如爬虫或机器学习算法，来识别和破解验证码。测试应该验证验证码对抗自动化攻击的效果，确保其足够复杂和多样性，难以被自动程序破解。因此，我们选择后端生成验证码。后端生成验证码是一种用于验证用户身份、防范自动化攻击的常见安全策略。系统可以选择不同类型的验证码，如数字验证码、字母验证码、数字与字母组合的验证码、数学运算验证码等。验证码的类型应该根据具体的安全需求和用户体验来选择。验证码的长度通常是可配置的，根据安全要求可以选择适当的长度。一般来说，验证码长度越长，破解的难度就越大。系统可以设置验证码的复杂性，包括使用大小写字母、数字、特殊字符等。增加验证码的复杂性可以提高安全性，但也需要注意不要使验证码过于复杂而难以识别。为了防止验证码被攻击者截获后长时间使用，验证码通常具有一定的过期时间。过期时间可以根据具体需求进行配置，例如设置为几分钟。同时，我们也要确保每个验证码的唯一性，防止攻击者通过重复使用相同的验证码进行攻击。使用合适的算法和策略确保验证码的唯一性。如果验证码需要通过网络传输到客户端，确保在传输过程中采用安全的通信协议，如HTTPS，以防止中间人攻击。对于需要频繁刷新验证码的场景，我们还要考虑实现动态刷新机制，减少恶意攻击的可能性。

性能测试
    性能测试是在软件开发过程中关键的一环，主要用于评估系统在不同负载条件下的性能、稳定性和可伸缩性。在进行性能测试时，可能会遇到一些常见的问题，下面是其中一些问题的描述：
        定义合适的性能指标： 在性能测试之前，需要明确定义系统的性能指标，例如响应时间、吞吐量、并发用户数等。不清晰或不准确的性能指标可能导致对系统性能的错误评估。
        负载模拟的真实性： 确保负载测试使用的负载模拟是真实和准确的。如果负载模拟不符合实际使用场景，测试结果可能不具有实际参考价值。
        测试环境的还原性： 测试环境的还原性是指测试环境是否能够准确地还原生产环境的特性。如果测试环境与生产环境存在显著差异，测试结果可能不准确。
        并发用户数设置： 确定适当的并发用户数是一个挑战。设置过低可能无法发现系统在高负载下的性能问题，而设置过高可能导致系统崩溃。需要根据系统的预期使用情况来调整并发用户数。
        测试数据的真实性： 使用真实和合适的测试数据对性能测试至关重要。如果测试数据不真实或不具有代表性，测试结果可能无法反映系统在真实场景下的表现。
        测试工具选择： 选择合适的性能测试工具是至关重要的。不同的工具适用于不同的场景，选择不当可能导致测试结果的不准确性。
        测试时间的选择： 性能测试应该在软件开发的早期阶段开始，并且要在整个软件生命周期中定期进行。选择测试的时间点不当可能导致对系统性能问题的遗漏。
        性能监控和分析： 确保在性能测试期间进行全面的监控和分析。及时识别和解决性能问题需要有效的监控工具和分析手段。
        持续集成的性能测试： 将性能测试整合到持续集成和持续交付流程中，确保每次代码更改都能进行必要的性能验证。
        容量规划： 根据性能测试结果进行容量规划，确保系统能够满足未来的用户和负载增长。

测试时遇见的问题
    origin和refer匹配问题
        在Web开发中，Origin 和 Referer（注意拼写是Referer而不是Referrer，尽管规范中使用的是Referrer，但由于历史原因，浏览器普遍使用Referer）是两个HTTP头字段，用于标识请求的来源。这两者经常用于实施跨站请求伪造（CSRF）和跨站脚本攻击（XSS）的防御机制。
        Origin： Origin 是一个包含协议、域名和端口的字符串，用于表示请求的来源。例如，https://www.example.com 是一个Origin。浏览器在发送跨源请求时，会将请求的Origin信息包含在请求头中。服务器可以通过检查这个信息来确定是否允许跨源请求。
        Referer： Referer 是一个包含完整URL的字符串，表示引导用户代理（通常是浏览器）发送当前请求的来源。例如，如果用户从https://www.example.com/page1点击链接跳转到https://www.example.com/page2，那么在发送到page2的请求头中会包含Referer: https://www.example.com/page1。

    server暴露使用的技术resty和jetty
        Resty 不是一个独立的服务器，而是一个基于 OpenResty 平台的 Lua web 框架。OpenResty（也被称为 ngx_openresty）是一个集成了 Nginx 服务器和一系列常用的第三方模块的高性能 Web 平台。
        OpenResty 提供了一种在 Nginx 服务器上通过 Lua 编程语言扩展和定制服务器行为的方法。Resty 则是一个基于这个平台的框架，它使得在 Nginx 中使用 Lua 编写的 web 应用变得更加简单和方便。
        Resty 主要用于构建基于 Nginx 的高性能、低延迟的 Web 服务，特别适用于处理大量并发请求的场景。
        Jetty：
        Jetty 是一个开源的、灵活的 Java HTTP 服务器和 Servlet 容器。它可以嵌入到 Java 应用程序中，也可以作为独立的服务器运行。
        Jetty 提供了一种轻量级、灵活的方式来构建 Java Web 应用程序，支持 Servlet、WebSocket、HTTP/2 等标准。Jetty 的嵌入式特性使得将其嵌入到应用程序中变得相对简单，同时也支持作为独立的服务器运行。
        Jetty 在 Java 生态系统中广泛应用，特别是在构建嵌入式应用、微服务、以及各种 Java Web 应用程序方面。
```