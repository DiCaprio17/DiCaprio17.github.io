---
layout:     post
title:      SpringMVC—学习笔记#day01
subtitle:   SpringMVC
date:       2019-08-06
author:     DiCaprio
header-img: img/post-bg-digital-native.jpeg
catalog: true
tags:
    - SpringMVC
    - Java
---

<p id="main-toc"><strong>目录</strong></p>


<p id="%E7%AC%AC%E4%B8%80%E7%AB%A0%EF%BC%9A%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E5%92%8CMVC-toc" style="margin-left:0px;"><a href="#%E7%AC%AC%E4%B8%80%E7%AB%A0%EF%BC%9A%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E5%92%8CMVC" rel="nofollow" data-token="d37e1d1207297347e0f738d8fdfb8181" target="_self">第一章：三层架构和MVC</a></p>
<p id="1.%20%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84-toc" style="margin-left:40px;"><a href="#1.%20%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84" rel="nofollow" data-token="2c4d91881f6e6a2f5eeea1035cdb0844" target="_self">1. 三层架构</a></p>
<p id="2.%20MVC%E6%A8%A1%E5%9E%8B-toc" style="margin-left:40px;"><a href="#2.%20MVC%E6%A8%A1%E5%9E%8B" rel="nofollow" data-token="a780fe15e103ea43df68cd66d0e8d6ac" target="_self">2. MVC模型</a></p>
<p id="%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9ASpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B-toc" style="margin-left:0px;"><a href="#%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9ASpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B" rel="nofollow" data-token="fa43ecb0f79fdfa4a883896b0e0f0d97" target="_self">第二章：SpringMVC的入门案例</a></p>
<p id="1.%20SpringMVC%E7%9A%84%E6%A6%82%E8%BF%B0-toc" style="margin-left:40px;"><a href="#1.%20SpringMVC%E7%9A%84%E6%A6%82%E8%BF%B0" rel="nofollow" data-token="fd7af2f999e9d642618d1837dad97264" target="_self">1. SpringMVC的概述</a></p>
<p style="margin-left:80px;"><a href="#1.%20SpringMVC%E7%9A%84%E6%A6%82%E8%BF%B0" rel="nofollow" data-token="fd7af2f999e9d642618d1837dad97264" target="_self">1. SpringMVC的概述</a></p>
<p id="2.%20SpringMVC%E5%9C%A8%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E4%B8%AD%E7%9A%84%E4%BD%8D%E7%BD%AE-toc" style="margin-left:80px;"><a href="#2.%20SpringMVC%E5%9C%A8%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E4%B8%AD%E7%9A%84%E4%BD%8D%E7%BD%AE" rel="nofollow" data-token="aa79a0ac4df6a5a9e04afbc9a0d19149" target="_self">2. SpringMVC在三层架构中的位置</a></p>
<p id="3.%20SpringMVC%E7%9A%84%E4%BC%98%E5%8A%BF-toc" style="margin-left:80px;"><a href="#3.%20SpringMVC%E7%9A%84%E4%BC%98%E5%8A%BF" rel="nofollow" data-token="811a11c6969a57c2902ee414c7e06af1" target="_self">3. SpringMVC的优势</a></p>
<p id="4.%20SpringMVC%E5%92%8CStruts2%E6%A1%86%E6%9E%B6%E7%9A%84%E5%AF%B9%E6%AF%94-toc" style="margin-left:80px;"><a href="#4.%20SpringMVC%E5%92%8CStruts2%E6%A1%86%E6%9E%B6%E7%9A%84%E5%AF%B9%E6%AF%94" rel="nofollow" data-token="3447b96df9619b07c9b4d25d69ef1753" target="_self">4. SpringMVC和Struts2框架的对比</a></p>
<p id="%C2%A02.%20SpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E7%A8%8B%E5%BA%8F-toc" style="margin-left:40px;"><a href="#%C2%A02.%20SpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E7%A8%8B%E5%BA%8F" rel="nofollow" data-token="f652e69c29f5ba1b95168e94e73d602a" target="_self">&nbsp;2. SpringMVC的入门程序</a></p>
<p id="1.%20%E5%88%9B%E5%BB%BAWEB%E5%B7%A5%E7%A8%8B%EF%BC%8C%E5%BC%95%E5%85%A5%E5%BC%80%E5%8F%91%E7%9A%84jar%E5%8C%85-toc" style="margin-left:80px;"><a href="#1.%20%E5%88%9B%E5%BB%BAWEB%E5%B7%A5%E7%A8%8B%EF%BC%8C%E5%BC%95%E5%85%A5%E5%BC%80%E5%8F%91%E7%9A%84jar%E5%8C%85" rel="nofollow" data-token="86c798d9bce5000e40c723e45eb3ef79" target="_self">1. 创建WEB工程，引入开发的jar包</a></p>
<p id="2.%20%E9%85%8D%E7%BD%AE%E6%A0%B8%E5%BF%83%E7%9A%84%E6%8E%A7%E5%88%B6%E5%99%A8%EF%BC%88%E9%85%8D%E7%BD%AEDispatcherServlet%EF%BC%89-toc" style="margin-left:80px;"><a href="#2.%20%E9%85%8D%E7%BD%AE%E6%A0%B8%E5%BF%83%E7%9A%84%E6%8E%A7%E5%88%B6%E5%99%A8%EF%BC%88%E9%85%8D%E7%BD%AEDispatcherServlet%EF%BC%89" rel="nofollow" data-token="49acd39c0031f5c1e98607182f91ba01" target="_self">2. 配置核心的控制器（配置DispatcherServlet）</a></p>
<p id="3.%E7%BC%96%E5%86%99springmvc.xml%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6-toc" style="margin-left:80px;"><a href="#3.%E7%BC%96%E5%86%99springmvc.xml%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6" rel="nofollow" data-token="2b957bb086f868c94ee22ffe4d5d9f46" target="_self">3.编写springmvc.xml的配置文件</a></p>
<p id="4.%20%E7%BC%96%E5%86%99index.jsp%E5%92%8CHelloController%E6%8E%A7%E5%88%B6%E5%99%A8%E7%B1%BB-toc" style="margin-left:80px;"><a href="#4.%20%E7%BC%96%E5%86%99index.jsp%E5%92%8CHelloController%E6%8E%A7%E5%88%B6%E5%99%A8%E7%B1%BB" rel="nofollow" data-token="8c8ba8a3c20951a453444de640e54378" target="_self">4. 编写index.jsp和HelloController控制器类</a></p>
<p id="5.%20%E5%9C%A8WEB-INF%E7%9B%AE%E5%BD%95%E4%B8%8B%E5%88%9B%E5%BB%BApages%E6%96%87%E4%BB%B6%E5%A4%B9%EF%BC%8C%E7%BC%96%E5%86%99success.jsp%E7%9A%84%E6%88%90%E5%8A%9F%E9%A1%B5%E9%9D%A2-toc" style="margin-left:80px;"><a href="#5.%20%E5%9C%A8WEB-INF%E7%9B%AE%E5%BD%95%E4%B8%8B%E5%88%9B%E5%BB%BApages%E6%96%87%E4%BB%B6%E5%A4%B9%EF%BC%8C%E7%BC%96%E5%86%99success.jsp%E7%9A%84%E6%88%90%E5%8A%9F%E9%A1%B5%E9%9D%A2" rel="nofollow" data-token="aa10278b14001251a0872ad43caee23a" target="_self">5. 在WEB-INF目录下创建pages文件夹，编写success.jsp的成功页面</a></p>
<p id="6.%20%E5%90%AF%E5%8A%A8Tomcat%E6%9C%8D%E5%8A%A1%E5%99%A8%EF%BC%8C%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95-toc" style="margin-left:80px;"><a href="#6.%20%E5%90%AF%E5%8A%A8Tomcat%E6%9C%8D%E5%8A%A1%E5%99%A8%EF%BC%8C%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95" rel="nofollow" data-token="7f74584502f5980cb57a4be2808b87de" target="_self">6. 启动Tomcat服务器，进行测试</a></p>
<p id="3.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B%E5%88%86%E6%9E%90-toc" style="margin-left:40px;"><a href="#3.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B%E5%88%86%E6%9E%90" rel="nofollow" data-token="eef835b1517680adc176adb135ee62fd" target="_self">3. 入门案例的执行过程分析</a></p>
<p id="1.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E6%B5%81%E7%A8%8B-toc" style="margin-left:80px;"><a href="#1.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E6%B5%81%E7%A8%8B" rel="nofollow" data-token="9c8a28c5ee34c277121a5849a3df2c22" target="_self">1. 入门案例的执行流程</a></p>
<p id="2.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E4%B8%AD%E7%9A%84%E7%BB%84%E4%BB%B6%E5%88%86%E6%9E%90-toc" style="margin-left:80px;"><a href="#2.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E4%B8%AD%E7%9A%84%E7%BB%84%E4%BB%B6%E5%88%86%E6%9E%90" rel="nofollow" data-token="7da3174c7121f129b0829aed6562cb64" target="_self">2. 入门案例中的组件分析</a></p>
<p id="3.%20RequestMapping%E6%B3%A8%E8%A7%A3-toc" style="margin-left:80px;"><a href="#3.%20RequestMapping%E6%B3%A8%E8%A7%A3" rel="nofollow" data-token="5a30121a93e7e747261c14d54ca5a384" target="_self">3. RequestMapping注解</a></p>
<p id="%E7%AC%AC%E4%B8%89%E7%AB%A0%EF%BC%9A%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A-toc" style="margin-left:0px;"><a href="#%E7%AC%AC%E4%B8%89%E7%AB%A0%EF%BC%9A%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A" rel="nofollow" data-token="34d8844f904e41c11482f1eece51c398" target="_self">第三章：请求参数的绑定</a></p>
<p id="1.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A%E8%AF%B4%E6%98%8E-toc" style="margin-left:40px;"><a href="#1.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A%E8%AF%B4%E6%98%8E" rel="nofollow" data-token="122395b87ac797d39a6de8be0fe89493" target="_self">1. 请求参数的绑定说明</a></p>
<p id="1.%20%E7%BB%91%E5%AE%9A%E6%9C%BA%E5%88%B6-toc" style="margin-left:80px;"><a href="#1.%20%E7%BB%91%E5%AE%9A%E6%9C%BA%E5%88%B6" rel="nofollow" data-token="ae94f86d3ad4941e7279124dca79f31a" target="_self">1. 绑定机制</a></p>
<p id="2.%20%E6%94%AF%E6%8C%81%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B-toc" style="margin-left:80px;"><a href="#2.%20%E6%94%AF%E6%8C%81%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B" rel="nofollow" data-token="ef0cfb35ef367a7dd38ac9837a27dcfc" target="_self">2. 支持的数据类型</a></p>
<p id="2.%20%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B-toc" style="margin-left:40px;"><a href="#2.%20%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B" rel="nofollow" data-token="859a7209235dc2ee8aa59d8f1aff7116" target="_self">2. 基本数据类型和字符串类型</a></p>
<p id="3.%20%E5%AE%9E%E4%BD%93%E7%B1%BB%E5%9E%8B%EF%BC%88JavaBean%EF%BC%89-toc" style="margin-left:40px;"><a href="#3.%20%E5%AE%9E%E4%BD%93%E7%B1%BB%E5%9E%8B%EF%BC%88JavaBean%EF%BC%89" rel="nofollow" data-token="0e2f6cb73f8f594ab3989572c91c4eda" target="_self">3. 实体类型（JavaBean）</a></p>
<p id="4.%20%E7%BB%99%E9%9B%86%E5%90%88%E5%B1%9E%E6%80%A7%E6%95%B0%E6%8D%AE%E5%B0%81%E8%A3%85-toc" style="margin-left:40px;"><a href="#4.%20%E7%BB%99%E9%9B%86%E5%90%88%E5%B1%9E%E6%80%A7%E6%95%B0%E6%8D%AE%E5%B0%81%E8%A3%85" rel="nofollow" data-token="8d322d47d3e3f9503b00a5ce619cff22" target="_self">4. 给集合属性数据封装</a></p>
<p id="5.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E8%A7%A3%E5%86%B3-toc" style="margin-left:40px;"><a href="#5.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E8%A7%A3%E5%86%B3" rel="nofollow" data-token="f86222e17f2bb15f0962193cc6f392c2" target="_self">5. 请求参数中文乱码的解决</a></p>
<p id="6.%20%E8%87%AA%E5%AE%9A%E4%B9%89%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2%E5%99%A8-toc" style="margin-left:40px;"><a href="#6.%20%E8%87%AA%E5%AE%9A%E4%B9%89%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2%E5%99%A8" rel="nofollow" data-token="b0535b91e1a94749403acdc2e5a12728" target="_self">6. 自定义类型转换器</a></p>
<p id="7.%20%E5%9C%A8%E6%8E%A7%E5%88%B6%E5%99%A8%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%8E%9F%E7%94%9F%E7%9A%84ServletAPI%E5%AF%B9%E8%B1%A1-toc" style="margin-left:40px;"><a href="#7.%20%E5%9C%A8%E6%8E%A7%E5%88%B6%E5%99%A8%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%8E%9F%E7%94%9F%E7%9A%84ServletAPI%E5%AF%B9%E8%B1%A1" rel="nofollow" data-token="703adeb67c6b4efba328e47a2e2ecd82" target="_self">7. 在控制器中使用原生的ServletAPI对象</a></p>
<p id="%E7%AC%AC4%E7%AB%A0%20%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3-toc" style="margin-left:0px;"><a href="#%E7%AC%AC4%E7%AB%A0%20%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3" rel="nofollow" data-token="838d6bd40b6952a50bb272f85190ede2" target="_self">第四章：常用注解</a></p>
<p id="RequestParam-toc" style="margin-left:40px;"><a href="#RequestParam" rel="nofollow" data-token="f2c63d0be4ead06607afcc8c2850ba28" target="_self">RequestParam</a></p>
<p id="RequestBody-toc" style="margin-left:40px;"><a href="#RequestBody" rel="nofollow" data-token="7f9edf75159a514f70177988ef196d1e" target="_self">RequestBody</a></p>
<p id="PathVaribale-toc" style="margin-left:40px;"><a href="#PathVaribale" rel="nofollow" data-token="68c4f50562756910e7cbd7852c322eec" target="_self">PathVaribale</a></p>
<p id="REST%20%E9%A3%8E%E6%A0%BC%20URL-toc" style="margin-left:80px;"><a href="#REST%20%E9%A3%8E%E6%A0%BC%20URL" rel="nofollow" data-token="7d0c8ad6f0062598fe0b6ae7d955e1ec" target="_self">REST 风格 URL</a></p>
<p id="%E5%9F%BA%E4%BA%8EHiddentHttpMethodFilter%E7%9A%84%E7%A4%BA%E4%BE%8B-toc" style="margin-left:80px;"><a href="#%E5%9F%BA%E4%BA%8EHiddentHttpMethodFilter%E7%9A%84%E7%A4%BA%E4%BE%8B" rel="nofollow" data-token="f66b8a927fe6dafa6015aff488296441" target="_self">基于HiddentHttpMethodFilter的示例</a></p>
<p id="RequestHeader-toc" style="margin-left:40px;"><a href="#RequestHeader" rel="nofollow" data-token="f3a40b3fc7e732ad30ec9b812b0f56db" target="_self">RequestHeader</a></p>
<p id="CookieValue-toc" style="margin-left:40px;"><a href="#CookieValue" rel="nofollow" data-token="b015fd05bd8da97fb40b31c75c16f6af" target="_self">CookieValue</a></p>
<p id="ModelAttribute-toc" style="margin-left:40px;"><a href="#ModelAttribute" rel="nofollow" data-token="d9cd454fb6882d002fcd9e22904942d3" target="_self">ModelAttribute</a></p>
<p id="SessionAttribute-toc" style="margin-left:40px;"><a href="#SessionAttribute" rel="nofollow" data-token="149cef6878bfe0f3303574fc5df66550" target="_self">SessionAttribute</a></p>
<hr id="hr-toc"><h1 id="%E7%AC%AC%E4%B8%80%E7%AB%A0%EF%BC%9A%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E5%92%8CMVC" style="margin-left:0cm;"><a name="t0"></a>第一章：三层架构和MVC</h1>

<h2 id="1.%20%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84" style="margin-left:0cm;"><a name="t1"></a>1. 三层架构</h2>
<p style="margin-left:0cm;"><strong>1. 咱们开发服务器端程序，一般都基于两种形式，一种C/S架构程序，一种B/S架构程序</strong></p>
<p style="margin-left:0cm;"><strong>2. 使用Java语言基本上都是开发B/S架构的程序，B/S架构又分成了三层架构</strong></p>
<p style="margin-left:0cm;"><strong>3. 三层架构</strong></p>
<ul><li style="margin-left:0cm;">1. 表现层：WEB层，用来和客户端进行数据交互的。表现层一般会采用MVC的设计模型</li>
	<li style="margin-left:0cm;">2. 业务层：处理公司具体的业务逻辑的</li>
	<li style="margin-left:0cm;">3. 持久层：用来操作数据库的</li>
</ul><h2 id="2.%20MVC%E6%A8%A1%E5%9E%8B" style="margin-left:0cm;"><a name="t2"></a>2. MVC模型</h2>

<blockquote>
<p style="margin-left:0cm;">1. MVC全名是Model View Controller 模型视图控制器，每个部分各司其职。</p>

<p style="margin-left:0cm;">2. Model：数据模型，JavaBean的类，用来进行数据封装。</p>
<p style="margin-left:0cm;">3. View：指JSP、HTML用来展示数据给用户</p>
<p style="margin-left:0cm;">4. Controller：用来接收用户的请求，整个流程的控制器。用来进行数据校验等。</p>
</blockquote>

<h1 id="%E7%AC%AC%E4%BA%8C%E7%AB%A0%EF%BC%9ASpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B" style="margin-left:0cm;"><a name="t3"></a>第二章：SpringMVC的入门案例</h1>
<h2 id="1.%20SpringMVC%E7%9A%84%E6%A6%82%E8%BF%B0" style="margin-left:0cm;"><a name="t4"></a>1. SpringMVC的概述</h2>
<h3 style="margin-left:0cm;"><a name="t5"></a>1. SpringMVC的概述</h3>
<blockquote>
<p style="margin-left:0cm;">1. 是一种基于Java实现的MVC设计模型的请求驱动类型的轻量级WEB框架。</p>

<p style="margin-left:0cm;">2. Spring MVC属于SpringFrameWork的后续产品，已经融合在Spring Web Flow里面。Spring 框架提供了构建 Web 应用程序的全功能 MVC 模块。</p>
<p style="margin-left:0cm;">3. 使用 Spring 可插入的 MVC 架构，从而在使用Spring进行WEB开发时，可以选择使用Spring的SpringMVC框架或集成其他MVC开发框架，如Struts1(现在一般不用)，Struts2等。</p>
<p style="margin-left:0cm;">SpringMVC 是一种基于 Java 的实现 MVC 设计模型的请求驱动类型的轻量级 Web 框架，属于 SpringFrameWork 的后续产品，已经融合在 Spring Web Flow 里面。Spring 框架提供了构建 Web 应用程序的全功能 MVC 模块。使用 Spring 可插入的 MVC 架构，从而在使用 Spring 进行 WEB 开发时，可以选择使用 Spring的 Spring MVC 框架或集成其他 MVC 开发框架，如 Struts1(现在一般不用)，Struts2 等。SpringMVC 已经成为目前最主流的 MVC 框架之一，并且随着 Spring3.0 的发布，全面超越 Struts2，成<br>
为最优秀的 MVC 框架。它通过一套注解，让一个简单的 Java 类成为处理请求的控制器，而无须实现任何接口。同时它还支持<br>
RESTful 编程风格的请求。</p>
</blockquote>

<h3 id="2.%20SpringMVC%E5%9C%A8%E4%B8%89%E5%B1%82%E6%9E%B6%E6%9E%84%E4%B8%AD%E7%9A%84%E4%BD%8D%E7%BD%AE" style="margin-left:0cm;"><a name="t6"></a>2. SpringMVC在三层架构中的位置</h3>
<blockquote>
<p style="margin-left:0cm;">表现层框架</p>
</blockquote>

<h3 id="3.%20SpringMVC%E7%9A%84%E4%BC%98%E5%8A%BF" style="margin-left:0cm;"><a name="t7"></a>3. SpringMVC的优势</h3>
<blockquote>
<p>1、清晰的角色划分：<br>
前端控制器（DispatcherServlet）<br>
请求到处理器映射（HandlerMapping）<br>
处理器适配器（HandlerAdapter）<br>
视图解析器（ViewResolver）<br>
处理器或页面控制器（Controller）<br>
验证器（ Validator）<br>
命令对象（Command 请求参数绑定到的对象就叫命令对象）<br>
表单对象（Form Object 提供给表单展示和提交到的对象就叫表单对象）。<br>
2、分工明确，而且扩展点相当灵活，可以很容易扩展，虽然几乎不需要。<br>
3、由于命令对象就是一个 POJO，无需继承框架特定 API，可以使用命令对象直接作为业务对象。<br>
4、和 Spring 其他框架无缝集成，是其它 Web 框架所不具备的。<br>
5、可适配，通过 HandlerAdapter 可以支持任意的类作为处理器。<br>
6、可定制性，HandlerMapping、ViewResolver 等能够非常简单的定制。<br>
7、功能强大的数据验证、格式化、绑定机制。<br>
8、利用 Spring 提供的 Mock 对象能够非常简单的进行 Web 层单元测试。<br>
9、本地化、主题的解析的支持，使我们更容易进行国际化和主题的切换。<br>
10、强大的 JSP 标签库，使 JSP 编写更容易。<br>
………………还有比如RESTful风格的支持、简单的文件上传、约定大于配置的契约式编程支持、基于注解的零配<br>
置支持等等。</p>
</blockquote>

<h3 id="4.%20SpringMVC%E5%92%8CStruts2%E6%A1%86%E6%9E%B6%E7%9A%84%E5%AF%B9%E6%AF%94" style="margin-left:0cm;"><a name="t8"></a>4. SpringMVC和Struts2框架的对比</h3>
<blockquote>
<p><strong>共同点：</strong><br>
它们都是表现层框架，都是基于 MVC 模型编写的。<br>
它们的底层都离不开原始 ServletAPI。<br>
它们处理请求的机制都是一个核心控制器。<br><strong>区别：</strong><br>
Spring MVC 的入口是 Servlet, 而 Struts2 是 Filter<br>
Spring MVC 是基于方法设计的，而 Struts2 是基于类，Struts2 每次执行都会创建一个动作类。所以 Spring MVC 会稍微比 Struts2 快些。<br>
Spring MVC 使用更加简洁,同时还支持 JSR303, 处理 ajax 的请求更方便(JSR303 是一套 JavaBean 参数校验的标准，它定义了很多常用的校验注解，我们可以直接将这些注解加在我们 JavaBean 的属性上面，就可以在需要校验的时候进行校验了。)<br>
Struts2 的 OGNL 表达式使页面的开发效率相比 Spring MVC 更高些，但执行效率并没有比 JSTL 提升，尤其是 struts2 的表单标签，远没有 html 执行效率高。</p>
</blockquote>

<h2 id="%C2%A02.%20SpringMVC%E7%9A%84%E5%85%A5%E9%97%A8%E7%A8%8B%E5%BA%8F"><a name="t9"></a>&nbsp;2. SpringMVC的入门程序</h2>
<h3 id="1.%20%E5%88%9B%E5%BB%BAWEB%E5%B7%A5%E7%A8%8B%EF%BC%8C%E5%BC%95%E5%85%A5%E5%BC%80%E5%8F%91%E7%9A%84jar%E5%8C%85" style="margin-left:0cm;"><a name="t10"></a>1. 创建WEB工程，引入开发的jar包</h3>
<p style="margin-left:0cm;"><img alt="" class="has" height="500" src="https://img-blog.csdnimg.cn/20190806173249768.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="769"></p>
<p style="margin-left:0cm;">具体的坐标如下</p>
<pre class="has" name="code"><code class="hljs xml"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">&lt;!-- 版本锁定 --&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-tag">&lt;<span class="hljs-name">properties</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">spring.version</span>&gt;</span>5.0.2.RELEASE<span class="hljs-tag">&lt;/<span class="hljs-name">spring.version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-tag">&lt;/<span class="hljs-name">properties</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-tag">&lt;<span class="hljs-name">dependencies</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">groupId</span>&gt;</span>org.springframework<span class="hljs-tag">&lt;/<span class="hljs-name">groupId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">artifactId</span>&gt;</span>spring-context<span class="hljs-tag">&lt;/<span class="hljs-name">artifactId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">version</span>&gt;</span>${spring.version}<span class="hljs-tag">&lt;/<span class="hljs-name">version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">groupId</span>&gt;</span>org.springframework<span class="hljs-tag">&lt;/<span class="hljs-name">groupId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">artifactId</span>&gt;</span>spring-web<span class="hljs-tag">&lt;/<span class="hljs-name">artifactId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="14"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">version</span>&gt;</span>${spring.version}<span class="hljs-tag">&lt;/<span class="hljs-name">version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="15"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="16"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="17"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">groupId</span>&gt;</span>org.springframework<span class="hljs-tag">&lt;/<span class="hljs-name">groupId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="18"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">artifactId</span>&gt;</span>spring-webmvc<span class="hljs-tag">&lt;/<span class="hljs-name">artifactId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="19"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">version</span>&gt;</span>${spring.version}<span class="hljs-tag">&lt;/<span class="hljs-name">version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="20"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="21"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="22"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">groupId</span>&gt;</span>javax.servlet<span class="hljs-tag">&lt;/<span class="hljs-name">groupId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="23"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">artifactId</span>&gt;</span>servlet-api<span class="hljs-tag">&lt;/<span class="hljs-name">artifactId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="24"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">version</span>&gt;</span>2.5<span class="hljs-tag">&lt;/<span class="hljs-name">version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="25"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">scope</span>&gt;</span>provided<span class="hljs-tag">&lt;/<span class="hljs-name">scope</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="26"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="27"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="28"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">groupId</span>&gt;</span>javax.servlet.jsp<span class="hljs-tag">&lt;/<span class="hljs-name">groupId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="29"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">artifactId</span>&gt;</span>jsp-api<span class="hljs-tag">&lt;/<span class="hljs-name">artifactId</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="30"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">version</span>&gt;</span>2.0<span class="hljs-tag">&lt;/<span class="hljs-name">version</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="31"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">scope</span>&gt;</span>provided<span class="hljs-tag">&lt;/<span class="hljs-name">scope</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="32"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">dependency</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="33"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">dependencies</span>&gt;</span></div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<h3 id="2.%20%E9%85%8D%E7%BD%AE%E6%A0%B8%E5%BF%83%E7%9A%84%E6%8E%A7%E5%88%B6%E5%99%A8%EF%BC%88%E9%85%8D%E7%BD%AEDispatcherServlet%EF%BC%89" style="margin-left:0cm;"><a name="t11"></a>2. 配置核心的控制器（配置DispatcherServlet）</h3>
<p style="margin-left:0cm;">在web.xml配置文件中核心控制器DispatcherServlet</p>
<pre class="has" name="code"><code class="hljs xml"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">&lt;!-- SpringMVC的核心控制器 发任何一个请求都会经过这个servlet--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">servlet</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">servlet-name</span>&gt;</span>dispatcherServlet<span class="hljs-tag">&lt;/<span class="hljs-name">servlet-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">servlet-class</span>&gt;</span>org.springframework.web.servlet.DispatcherServlet<span class="hljs-tag">&lt;/<span class="hljs-name">servlet-class</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">&lt;!--让servlet去加载springmvc.xml文件--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">init-param</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">param-name</span>&gt;</span>contextConfigLocation<span class="hljs-tag">&lt;/<span class="hljs-name">param-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">param-value</span>&gt;</span>classpath:springmvc.xml<span class="hljs-tag">&lt;/<span class="hljs-name">param-value</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">init-param</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">&lt;!--servlet一创建就就加载springmvc.xml文件--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">load-on-startup</span>&gt;</span>1<span class="hljs-tag">&lt;/<span class="hljs-name">load-on-startup</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">servlet</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">servlet-mapping</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="14"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">servlet-name</span>&gt;</span>dispatcherServlet<span class="hljs-tag">&lt;/<span class="hljs-name">servlet-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="15"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">url-pattern</span>&gt;</span>/<span class="hljs-tag">&lt;/<span class="hljs-name">url-pattern</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="16"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">servlet-mapping</span>&gt;</span></div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<h3 id="3.%E7%BC%96%E5%86%99springmvc.xml%E7%9A%84%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6" style="margin-left:0cm;"><a name="t12"></a>3.编写springmvc.xml的配置文件</h3>
<pre class="has" name="code"><code class="hljs xml"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="php"><span class="hljs-meta">&lt;?</span>xml version=<span class="hljs-string">"1.0"</span> encoding=<span class="hljs-string">"UTF-8"</span><span class="hljs-meta">?&gt;</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-tag">&lt;<span class="hljs-name">beans</span> <span class="hljs-attr">xmlns</span>=<span class="hljs-string">"http://www.springframework.org/schema/beans"</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">       <span class="hljs-attr">xmlns:mvc</span>=<span class="hljs-string">"http://www.springframework.org/schema/mvc"</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">       <span class="hljs-attr">xmlns:context</span>=<span class="hljs-string">"http://www.springframework.org/schema/context"</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">       <span class="hljs-attr">xmlns:xsi</span>=<span class="hljs-string">"http://www.w3.org/2001/XMLSchema-instance"</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">       <span class="hljs-attr">xsi:schemaLocation</span>=<span class="hljs-string"><span class="hljs-string">"</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/beans</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/beans/spring-beans.xsd</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/mvc</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/mvc/spring-mvc.xsd</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/context</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-string">        http://www.springframework.org/schema/context/spring-context.xsd"</span>&gt;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="14"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!-- 配置spring创建容器时要注解扫描的包 --&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="15"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">context:component-scan</span> <span class="hljs-attr">base-package</span>=<span class="hljs-string">"cn.itcast"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">context:component-scan</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="16"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="17"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!-- 配置视图解析器 --&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="18"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">bean</span> <span class="hljs-attr">id</span>=<span class="hljs-string">"internalResourceViewResolver"</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="19"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">          <span class="hljs-attr">class</span>=<span class="hljs-string">"org.springframework.web.servlet.view.InternalResourceViewResolver"</span>&gt;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="20"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">&lt;!--文件所在目录--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="21"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">property</span> <span class="hljs-attr">name</span>=<span class="hljs-string">"prefix"</span> <span class="hljs-attr">value</span>=<span class="hljs-string">"/WEB-INF/pages/"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">property</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="22"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">&lt;!--文件后缀名--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="23"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">property</span> <span class="hljs-attr">name</span>=<span class="hljs-string">"suffix"</span> <span class="hljs-attr">value</span>=<span class="hljs-string">".jsp"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">property</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="24"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">bean</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="25"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="26"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!-- 配置spring开启注解mvc的支持--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="27"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">mvc:annotation-driven</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">mvc:annotation-driven</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="28"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-tag">&lt;/<span class="hljs-name">beans</span>&gt;</span></div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<h3 id="4.%20%E7%BC%96%E5%86%99index.jsp%E5%92%8CHelloController%E6%8E%A7%E5%88%B6%E5%99%A8%E7%B1%BB" style="margin-left:0cm;"><a name="t13"></a>4. 编写index.jsp和HelloController控制器类</h3>
<p style="margin-left:0cm;">index.jsp</p>
<p style="margin-left:0cm;"><img alt="" class="has" height="149" src="https://img-blog.csdnimg.cn/20190806184055882.png" width="317"></p>
<p style="margin-left:0cm;">HelloController</p>
<p style="margin-left:0cm;"><img alt="" class="has" height="200" src="https://img-blog.csdnimg.cn/20190806184124718.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="674"></p>
<h3 id="5.%20%E5%9C%A8WEB-INF%E7%9B%AE%E5%BD%95%E4%B8%8B%E5%88%9B%E5%BB%BApages%E6%96%87%E4%BB%B6%E5%A4%B9%EF%BC%8C%E7%BC%96%E5%86%99success.jsp%E7%9A%84%E6%88%90%E5%8A%9F%E9%A1%B5%E9%9D%A2" style="margin-left:0cm;"><a name="t14"></a>5. 在WEB-INF目录下创建pages文件夹，编写success.jsp的成功页面</h3>
<p style="margin-left:0cm;"><img alt="" class="has" height="293" src="https://img-blog.csdnimg.cn/20190806184209317.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="730"></p>
<h3 id="6.%20%E5%90%AF%E5%8A%A8Tomcat%E6%9C%8D%E5%8A%A1%E5%99%A8%EF%BC%8C%E8%BF%9B%E8%A1%8C%E6%B5%8B%E8%AF%95" style="margin-left:0cm;"><a name="t15"></a>6. 启动Tomcat服务器，进行测试</h3>
<p style="margin-left:0cm;"><img alt="" class="has" height="45" src="https://img-blog.csdnimg.cn/20190806184228619.png" width="444"></p>
<h2 id="3.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B%E5%88%86%E6%9E%90" style="margin-left:0cm;"><a name="t16"></a>3. 入门案例的执行过程分析</h2>
<h3 id="1.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E7%9A%84%E6%89%A7%E8%A1%8C%E6%B5%81%E7%A8%8B" style="margin-left:0cm;"><a name="t17"></a>1. 入门案例的执行流程</h3>
<blockquote>
<p style="margin-left:0cm;">1. 当启动Tomcat服务器的时候，因为配置了load-on-startup标签，所以会创建DispatcherServlet对象，就会加载springmvc.xml配置文件</p>

<p style="margin-left:0cm;">2. 开启了注解扫描，那么HelloController对象就会被创建</p>
<p style="margin-left:0cm;">3. 从index.jsp发送请求，请求会先到达DispatcherServlet核心控制器，根据配置@RequestMapping注解找到执行的具体方法</p>
<p style="margin-left:0cm;">4. 根据执行方法的返回值，再根据配置的视图解析器，去指定的目录下查找指定名称的JSP文件</p>
<p style="margin-left:0cm;">5. Tomcat服务器渲染页面，做出响应</p>
</blockquote>

<p id="%E2%80%8B" style="margin-left:0cm;"><img alt="" class="has" height="382" src="https://img-blog.csdnimg.cn/20190808122421189.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="868"></p>
<p style="margin-left:0cm;"><img alt="" class="has" height="480" src="https://img-blog.csdnimg.cn/20190808122508954.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="872"></p>
<h3 id="2.%20%E5%85%A5%E9%97%A8%E6%A1%88%E4%BE%8B%E4%B8%AD%E7%9A%84%E7%BB%84%E4%BB%B6%E5%88%86%E6%9E%90"><a name="t18"></a>2. 入门案例中的组件分析</h3>
<p style="margin-left:0cm;"><strong>1. 前端控制器（DispatcherServlet）</strong></p>
<blockquote>
<p style="margin-left:0cm;">用户请求到达前端控制器，它就相当于 mvc 模式中的 c，dispatcherServlet 是整个流程控制的中心，由它调用其它组件处理用户的请求，dispatcherServlet 的存在降低了组件之间的耦合性。</p>
</blockquote>

<p style="margin-left:0cm;"><strong>2. 处理器映射器（HandlerMapping）</strong></p>
<blockquote>
<p style="margin-left:0cm;">HandlerMapping 负责根据用户请求找到 Handler 即处理器，SpringMVC 提供了不同的映射器实现不同的映射方式，例如：配置文件方式，实现接口方式，注解方式等。</p>
</blockquote>

<p style="margin-left:0cm;"><strong>3. 处理器（Handler）</strong></p>
<blockquote>
<p style="margin-left:0cm;">它就是我们开发中要编写的具体业务控制器。由 DispatcherServlet 把用户请求转发到 Handler。由Handler 对具体的用户请求进行处理。</p>
</blockquote>

<p style="margin-left:0cm;"><strong>4. 处理器适配器（HandlAdapter）</strong></p>
<blockquote>
<p style="margin-left:0cm;">通过 HandlerAdapter 对处理器进行执行，这是适配器模式的应用，通过扩展适配器可以对更多类型的处理器进行执行。</p>

<p style="margin-left:0cm;"><img alt="" class="has" height="201" src="https://img-blog.csdnimg.cn/20190808123340607.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="649"></p>
</blockquote>

<p style="margin-left:0cm;"><strong>5. 视图解析器（View Resolver）</strong></p>
<blockquote>
<p style="margin-left:0cm;">View Resolver 负责将处理结果生成 View 视图，View Resolver 首先根据逻辑视图名解析成物理视图名即具体的页面地址，再生成 View 视图对象，最后对 View 进行渲染将处理结果通过页面展示给用户。</p>
</blockquote>

<p style="margin-left:0cm;"><strong>6. 视图（View）</strong></p>
<blockquote>
<p style="margin-left:0cm;">SpringMVC 框架提供了很多的 View 视图类型的支持，包括：jstlView、freemarkerView、pdfView等。我们最常用的视图就是 jsp。<br>
一般情况下需要通过页面标签或页面模版技术将模型数据通过页面展示给用户，需要由程序员根据业务需求开发具体的页面。</p>
</blockquote>

<p style="margin-left:0cm;"><strong>7.&lt;mvc:annotation-driven&gt;说明</strong></p>
<blockquote>
<p style="margin-left:0cm;">在 SpringMVC 的各个组件中，处理器映射器、处理器适配器、视图解析器称为 SpringMVC 的三大组件。<br>
使用 &lt;mvc:annotation-driven&gt; 自 动加载 RequestMappingHandlerMapping （处理映射器） 和RequestMappingHandlerAdapter （ 处 理 适 配 器 ） ， 可 用 在 SpringMVC.xml 配 置 文 件 中 使 用&lt;mvc:annotation-driven&gt;替代注解处理器和适配器的配置。</p>

<p style="margin-left:0cm;">它就相当于在 xml 中配置了：<br>
&lt;!-- 上面的标签相当于 如下配置--&gt;<br>
&lt;!-- Begin --&gt;<br>
&lt;!-- HandlerMapping --&gt;<br>
&lt;beanclass="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerM<br>
apping"&gt;&lt;/bean&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.handler.BeanNameUrlHandlerMapping"&gt;&lt;/bean&gt;<br>
&lt;!-- HandlerAdapter --&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerA<br>
dapter"&gt;&lt;/bean&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.HttpRequestHandlerAdapter"&gt;&lt;/bean&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.SimpleControllerHandlerAdapter"&gt;&lt;/bean&gt;<br>
&lt;!-- HadnlerExceptionResolvers --&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.method.annotation.ExceptionHandlerExcept<br>
ionResolver"&gt;&lt;/bean&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.annotation.ResponseStatusExceptionResolv<br>
er"&gt;&lt;/bean&gt;<br>
&lt;bean<br>
class="org.springframework.web.servlet.mvc.support.DefaultHandlerExceptionResolver"<br>
&gt;&lt;/bean&gt;<br>
&lt;!-- End --&gt;<br><strong>注意：</strong><br>
一般开发中，我们都需要写上此标签（虽然从入门案例中看，我们不写也行，随着课程的深入，该标签还有具体的使用场景）。<br><strong>明确：</strong><br>
我们只需要编写处理具体业务的控制器以及视图。</p>
</blockquote>

<h3 id="3.%20RequestMapping%E6%B3%A8%E8%A7%A3" style="margin-left:0cm;"><a name="t19"></a>3. RequestMapping注解</h3>
<blockquote>
<p>源码：<br>
@Target({ElementType.METHOD, ElementType.TYPE})<br>
@Retention(RetentionPolicy.RUNTIME)<br>
@Documented<br>
@Mapping<br>
public @interface RequestMapping {<br>
}<br><strong>作用：</strong><br>
用于建立请求 URL 和处理请求方法之间的对应关系。</p>

<p><strong>出现位置：</strong><br><em><u>类上：</u></em><br>
请求 URL 的<strong>第一级访问目录</strong>。此处不写的话，就相当于应用的根目录。写的话需要以/开头。<br>
它出现的目的是为了使我们的 URL 可以按照模块化管理:<br>
例如：<br>
账户模块：<br><span style="color:#f33b45;">/account</span>/add<br><span style="color:#f33b45;">/account</span>/update<br><span style="color:#f33b45;">/account</span>/delete<br>
...<br>
订单模块：<br><span style="color:#f33b45;">/order</span>/add<br><span style="color:#f33b45;">/order</span>/update<br><span style="color:#f33b45;">/order</span>/delete<br>
红色的部分就是把 RequsetMappding 写在类上，使我们的 URL 更加精细。<br><em><u>方法上：</u></em><br>
请求 URL 的<strong>第二级访问目录</strong>。<br><strong>属性：</strong><br>
value：用于指定请求的 URL。它和 path 属性的作用是一样的。<br>
method：用于指定请求的方式。<br>
params：用于指定限制请求参数的条件。它支持简单的表达式。要求请求参数的 key 和 value 必须和<br>
配置的一模一样。<br>
例如：<br>
params = {"accountName"}，表示请求参数必须有 accountName<br>
params = {"accountName=hh"}，表示请求参数必须有 accountName，且值必须为hh<img alt="" class="has" height="22" src="https://img-blog.csdnimg.cn/201908081259084.png" width="436"><br>
params = {"moeny!100"}，表示请求参数中 money 不能是 100。<br>
headers：用于指定限制请求消息头的条件。<br><strong>注意：</strong><br>
以上四个属性只要出现 2 个或以上时，他们的关系是与的关系。</p>
</blockquote>

<h1 id="%E7%AC%AC%E4%B8%89%E7%AB%A0%EF%BC%9A%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A" style="margin-left:0cm;"><a name="t20"></a>第三章：请求参数的绑定</h1>
<h2 id="1.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E7%9A%84%E7%BB%91%E5%AE%9A%E8%AF%B4%E6%98%8E" style="margin-left:0cm;"><a name="t21"></a>1. 请求参数的绑定说明</h2>
<h3 id="1.%20%E7%BB%91%E5%AE%9A%E6%9C%BA%E5%88%B6" style="margin-left:0cm;"><a name="t22"></a>1. 绑定机制</h3>
<blockquote>
<p style="margin-left:0cm;">1. 表单提交的数据都是k=v格式的 username=haha&amp;password=123</p>

<p style="margin-left:0cm;">2. SpringMVC的参数绑定过程是把表单提交的请求参数，作为控制器中方法的参数进行绑定的</p>
<p style="margin-left:0cm;">3. 要求：提交表单的name和参数的名称是相同的</p>
</blockquote>

<h3 id="2.%20%E6%94%AF%E6%8C%81%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B" style="margin-left:0cm;"><a name="t23"></a>2. 支持的数据类型</h3>
<blockquote>
<p style="margin-left:0cm;">1. 基本数据类型和字符串类型</p>

<p style="margin-left:0cm;">要求我们的参数名称必须和控制器中方法的形参名称保持一致。(严格区分大小写)</p>
<p style="margin-left:0cm;">2. POJO类型&nbsp; 包括实体类，以及关联的实体类（JavaBean）</p>
<p style="margin-left:0cm;">要求表单中参数名称和 POJO 类的属性名称保持一致。并且控制器方法的参数类型是 POJO 类型</p>
<p style="margin-left:0cm;">3. 集合数据类型（List、map集合等）</p>
<p style="margin-left:0cm;">第一种：<br>
要求集合类型的请求参数必须在 POJO 中。在表单中请求参数名称要和 POJO 中集合属性名称相同。<br>
给 List 集合中的元素赋值，使用下标。<br>
给 Map 集合中的元素赋值，使用键值对。<br>
第二种：<br>
接收的请求参数是 json 格式数据。需要借助一个注解实现。</p>

<p style="margin-left:0cm;">SpringMVC 绑定请求参数是自动实现的，但是要想使用，必须遵循使用要求</p>
</blockquote>

<h2 id="2.%20%E5%9F%BA%E6%9C%AC%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E5%92%8C%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B" style="margin-left:0cm;"><a name="t24"></a>2. 基本数据类型和字符串类型</h2>
<p style="margin-left:0cm;">1. 提交表单的name和参数的名称是相同的</p>
<p style="margin-left:0cm;"><img alt="" class="has" height="44" src="https://img-blog.csdnimg.cn/20190808151532923.png" width="676"></p>
<p style="margin-left:0cm;"><img alt="" class="has" height="248" src="https://img-blog.csdnimg.cn/20190808131213565.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="520"></p>
<p style="margin-left:0cm;">2. 区分大小写</p>
<h2 id="3.%20%E5%AE%9E%E4%BD%93%E7%B1%BB%E5%9E%8B%EF%BC%88JavaBean%EF%BC%89" style="margin-left:0cm;"><a name="t25"></a>3. 实体类型（JavaBean）</h2>
<p style="margin-left:0cm;">1. 提交表单的name和JavaBean中的属性名称需要一致</p>
<p style="margin-left:0cm;"><img alt="" class="has" height="197" src="https://img-blog.csdnimg.cn/20190808151608867.png" width="521"></p>
<p style="margin-left:0cm;"><img alt="" class="has" height="221" src="https://img-blog.csdnimg.cn/2019080815151097.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="409"></p>
<p style="margin-left:0cm;">2. 如果一个JavaBean类中包含其他的引用类型，那么表单的name属性需要编写成：对象.属性 例如：</p>
<p style="margin-left:0cm;">address.name</p>
<h2 id="4.%20%E7%BB%99%E9%9B%86%E5%90%88%E5%B1%9E%E6%80%A7%E6%95%B0%E6%8D%AE%E5%B0%81%E8%A3%85" style="margin-left:0cm;"><a name="t26"></a>4. 给集合属性数据封装</h2>
<p style="margin-left:0cm;">JSP页面编写方式：list[0].属性</p>
<p style="margin-left:0cm;"><img alt="" class="has" height="291" src="https://img-blog.csdnimg.cn/20190808151758853.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="576"></p>
<h2 id="5.%20%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E8%A7%A3%E5%86%B3" style="margin-left:0cm;"><a name="t27"></a>5. 请求参数中文乱码的解决</h2>
<p style="margin-left:0cm;">&nbsp;在web.xml中配置Spring提供的过滤器类</p>
<pre class="has" name="code"><code class="hljs xml"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!--配置解决中文乱码的过滤器--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">filter</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">filter-name</span>&gt;</span>characterEncodingFilter<span class="hljs-tag">&lt;/<span class="hljs-name">filter-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">filter-class</span>&gt;</span>org.springframework.web.filter.CharacterEncodingFilter<span class="hljs-tag">&lt;/<span class="hljs-name">filter-class</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">init-param</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">param-name</span>&gt;</span>encoding<span class="hljs-tag">&lt;/<span class="hljs-name">param-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">param-value</span>&gt;</span>UTF-8<span class="hljs-tag">&lt;/<span class="hljs-name">param-value</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">init-param</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">filter</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">filter-mapping</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">filter-name</span>&gt;</span>characterEncodingFilter<span class="hljs-tag">&lt;/<span class="hljs-name">filter-name</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">url-pattern</span>&gt;</span>/*<span class="hljs-tag">&lt;/<span class="hljs-name">url-pattern</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">filter-mapping</span>&gt;</span></div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<h2 id="6.%20%E8%87%AA%E5%AE%9A%E4%B9%89%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2%E5%99%A8" style="margin-left:0cm;"><a name="t28"></a>6. 自定义类型转换器</h2>
<p style="margin-left:0cm;">1. 表单提交的任何数据类型全部都是字符串类型，但是后台定义Integer类型，数据也可以封装上，说明Spring框架内部会默认进行数据类型转换。</p>
<p style="margin-left:0cm;">2. 如果想自定义数据类型转换，可以实现Converter的接口</p>
<blockquote>
<p style="margin-left:0cm;">1. 自定义类型转换器</p>

<pre class="has" name="code"><code class="hljs php"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment"><span class="hljs-comment">/**</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment"> * 把字符串转换日期</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment"> */</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-keyword">public</span> <span class="hljs-class"><span class="hljs-keyword">class</span> <span class="hljs-title">StringToDateConverter</span> <span class="hljs-keyword">implements</span> <span class="hljs-title">Converter</span>&lt;<span class="hljs-title">String</span>, <span class="hljs-title">Date</span>&gt; </span>{</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment"><span class="hljs-comment">/**</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * String source    传入进来字符串</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     *</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@param</span> source</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@return</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     */</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-keyword">public</span> Date convert(String source) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">// 判断</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="14"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">if</span> (source == <span class="hljs-keyword">null</span>) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="15"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-keyword">throw</span> <span class="hljs-keyword">new</span> RuntimeException(<span class="hljs-string">"请您传入数据"</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="16"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        }</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="17"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        DateFormat df = <span class="hljs-keyword">new</span> SimpleDateFormat(<span class="hljs-string">"yyyy-MM-dd"</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="18"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="19"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">try</span> {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="20"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-comment">// 把字符串转换日期</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="21"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-keyword">return</span> df.parse(source);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="22"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        } <span class="hljs-keyword">catch</span> (<span class="hljs-keyword">Exception</span> e) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="23"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-keyword">throw</span> <span class="hljs-keyword">new</span> RuntimeException(<span class="hljs-string">"数据类型转换出现错误"</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="24"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        }</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="25"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    }</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="26"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">}</div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<p>2. 注册自定义类型转换器，在springmvc.xml配置文件中编写配置</p>
<pre class="has" name="code"><code class="hljs xml"><ol class="hljs-ln" style="width:968px"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!--配置自定义类型转换器，注册转换器--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">bean</span> <span class="hljs-attr">id</span>=<span class="hljs-string">"conversionService"</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"org.springframework.context.support.ConversionServiceFactoryBean"</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;<span class="hljs-name">property</span> <span class="hljs-attr">name</span>=<span class="hljs-string">"converters"</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;<span class="hljs-name">set</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">                <span class="hljs-tag">&lt;<span class="hljs-name">bean</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"cn.itcast.utils.StringToDateConverter"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">bean</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">            <span class="hljs-tag">&lt;/<span class="hljs-name">set</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-tag">&lt;/<span class="hljs-name">property</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;/<span class="hljs-name">bean</span>&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment">&lt;!-- 配置spring开启注解mvc的支持，让上面的转换器生效--&gt;</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-tag">&lt;<span class="hljs-name">mvc:annotation-driven</span> <span class="hljs-attr">conversion-service</span>=<span class="hljs-string">"conversionService"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-name">mvc:annotation-driven</span>&gt;</span></div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
</blockquote>

<h2 id="7.%20%E5%9C%A8%E6%8E%A7%E5%88%B6%E5%99%A8%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%8E%9F%E7%94%9F%E7%9A%84ServletAPI%E5%AF%B9%E8%B1%A1" style="margin-left:0cm;"><a name="t29"></a>7. 在控制器中使用原生的ServletAPI对象</h2>
<p style="margin-left:0cm;">&nbsp;只需要在控制器的方法参数定义HttpServletRequest和HttpServletResponse对象</p>
<blockquote>
<p style="margin-left:0cm;">SpringMVC 还支持使用原始 ServletAPI 对象作为控制器方法的参数。支持原始 ServletAPI 对象有：<br>
HttpServletRequest<br>
HttpServletResponse<br>
HttpSession<br>
java.security.Principal<br>
Locale<br>
InputStream<br>
OutputStream<br>
Reader<br>
Writer<br>
我们可以把上述对象，直接写在控制的方法参数中使用。</p>
</blockquote>

<p style="margin-left:0cm;"><img alt="" class="has" height="24" src="https://img-blog.csdnimg.cn/20190808153419877.png" width="435"></p>
<p style="margin-left:0cm;"><img alt="" class="has" height="400" src="https://img-blog.csdnimg.cn/20190808153445254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="773"><img alt="" class="has" height="400" src="https://img-blog.csdnimg.cn/20190808153619657.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="766"></p>
<h1 id="%E7%AC%AC4%E7%AB%A0%20%E5%B8%B8%E7%94%A8%E6%B3%A8%E8%A7%A3" style="margin-left:0cm;"><a name="t30"></a>第四章：常用注解</h1>
<h2 id="RequestParam"><a name="t31"></a>RequestParam</h2>
<blockquote>
<p>作用：<br>
把请求中指定名称的参数给控制器中的形参赋值。<br>
属性：<br>
value：请求参数中的名称。<br>
required：请求参数中是否必须提供此参数。默认值：true。表示必须提供，如果不提供将报错。</p>
</blockquote>

<p><img alt="" class="has" height="27" src="https://img-blog.csdnimg.cn/20190808154213910.png" width="525">此时使用username都不行，参数只能是name</p>
<p><img alt="" class="has" height="131" src="https://img-blog.csdnimg.cn/20190808154146850.png" width="688"></p>
<h2 id="RequestBody"><a name="t32"></a>RequestBody</h2>
<blockquote>
<p>作用：<br>
用于获取请求体内容。直接使用得到是 key=value&amp;key=value...结构的数据。<br>
get 请求方式不适用。<br>
属性：<br>
required：是否必须有请求体。默认值是:true。当取值为 true 时,get 请求方式会报错。如果取值为 false，get 请求得到是 null。</p>
</blockquote>

<p><img alt="" class="has" height="106" src="https://img-blog.csdnimg.cn/20190808154634145.png" width="496"></p>
<p><img alt="" class="has" height="225" src="https://img-blog.csdnimg.cn/20190808154645414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="517"></p>
<p><img alt="" class="has" height="50" src="https://img-blog.csdnimg.cn/20190808154745675.png" width="175"></p>
<h2 id="PathVaribale"><a name="t33"></a>PathVaribale</h2>
<blockquote>
<p>作用：<br>
用于绑定 url 中的占位符。例如：请求 url 中 /delete/{id}，这个{id}就是 url 占位符。<br>
url 支持占位符是 spring3.0 之后加入的。是 springmvc 支持 rest 风格 URL 的一个重要标志。<br>
属性：<br>
value：用于指定 url 中占位符名称。<br>
required：是否必须提供占位符。</p>
</blockquote>

<h3 id="REST%20%E9%A3%8E%E6%A0%BC%20URL"><a name="t34"></a>REST 风格 URL</h3>
<blockquote>
<p>什么是 rest ：<br>
REST（英文：Representational State Transfer，简称 REST）描述了一个架构样式的网络系统，比如 web 应用程序。它首次出现在 2000 年 Roy Fielding 的博士论文中，他是 HTTP 规范的主要编写者之一。在目前主流的三种 Web 服务交互方案中，REST 相比于 SOAP（Simple Object Access protocol，简单对象访问协议）以及 XML-RPC 更加简单明了，无论是对 URL 的处理还是对 Payload 的编码，REST 都倾向于用更加简单轻量的方法设计和实现。值得注意的是 REST 并没有一个明确的标准，而更像是一种设计的风格。它本身并没有什么实用性，其核心价值在于如何设计出符合 REST 风格的网络接口。<br>
restful &nbsp;的优点<br>
它结构清晰、符合标准、易于理解、扩展方便，所以正得到越来越多网站的采用。<br>
restful &nbsp;的特性：<br>
资源（ Resources）：网络上的一个实体，或者说是网络上的一个具体信息。<br>
它可以是一段文本、一张图片、一首歌曲、一种服务，总之就是一个具体的存在。可以用一个 URI（统一资源定位符）指向它，每种资源对应一个特定的 URI 。要获取这个资源，访问它的 URI 就可以，因此 URI 即为每一个资源的独一无二的识别符。<br>
表现层（ Representation）：把资源具体呈现出来的形式，叫做它的表现层 （ Representation）。比如，文本可以用 txt 格式表现，也可以用 HTML 格式、XML 格式、JSON 格式表现，甚至可以采用二进制格式。<br>
状态转化（ State Transfer）：每 发出一个请求，就代表了客户端和服务器的一次交互过程。<br>
HTTP 协议，是一个无状态协议，即所有的状态都保存在服务器端。因此，如果客户端想要操作服务器，必须通过某种手段，让服务器端发生 “状态转化 ”（ State Tran sfer）。而这种转化是建立在表现层之上的，所以就是 &nbsp;“表现层状态转化 ”。具体说，就是 &nbsp;HTTP 协议里面，四个表示操作方式的动词： GET、 POST、 PUT、DELETE。它们分别对应四种基本操作： GET 用来获取资源， POST 用来新建资源， PUT 用来更新资源， DELETE 用来删除资源。</p>

<p><br>
restful &nbsp;的示例：<br>
/account/1 HTTP &nbsp;GET ： &nbsp;得到 id = 1 的 account<br>
/account/1 HTTP &nbsp;DELETE： 删除 id = 1 的 account<br>
/account/1 HTTP &nbsp;PUT： &nbsp;更新 id = 1 的 account<br>
/account HTTP &nbsp;POST： &nbsp;新增 account</p>
</blockquote>

<p><img alt="" class="has" height="453" src="https://img-blog.csdnimg.cn/20190808155408294.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"></p>
<p><img alt="" class="has" height="23" src="https://img-blog.csdnimg.cn/20190808155823799.png" width="491"></p>
<p><img alt="" class="has" height="226" src="https://img-blog.csdnimg.cn/20190808155836663.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="631"></p>
<h3 id="%E5%9F%BA%E4%BA%8EHiddentHttpMethodFilter%E7%9A%84%E7%A4%BA%E4%BE%8B"><a name="t35"></a>基于HiddentHttpMethodFilter的示例</h3>
<blockquote>
<p>作用：<br>
由于浏览器 form 表单只支持 GET 与 POST 请求，而 DELETE、PUT 等 method 并不支持，Spring3.0 添加了一个过滤器，可以将浏览器请求改为指定的请求方式，发送给我们的控制器方法，使得支持 GET、POST、PUT与 DELETE 请求。<br>
使用方法：<br>
第一步：在 web.xml 中配置该过滤器。<br>
第二步：请求方式必须使用 post 请求。<br>
第三步：按照要求提供_method 请求参数，该参数的取值就是我们需要的请求方式。</p>
</blockquote>

<h2 id="RequestHeader"><a name="t36"></a>RequestHeader</h2>
<blockquote>
<p>作用：<br>
用于获取请求消息头。<br>
属性：<br>
value：提供消息头名称<br>
required：是否必须有此消息头<br>
注：<br>
在实际开发中一般不怎么用。</p>
</blockquote>

<p><img alt="" class="has" height="28" src="https://img-blog.csdnimg.cn/20190808160415435.png" width="465"></p>
<pre class="has" name="code"><code class="hljs kotlin"><ol class="hljs-ln" style="width:1440px"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-meta">@RequestMapping(value = <span class="hljs-meta-string">"/testRequestHeader"</span>)</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-keyword">public</span> String testRequestHeader(<span class="hljs-meta">@RequestHeader(value = <span class="hljs-meta-string">"Accept"</span>)</span> String header, HttpServletRequest request, HttpServletResponse response) throws IOException {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(<span class="hljs-string">"执行了..."</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(header);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">// return "success";</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">// response.sendRedirect(request.getContextPath()+"/anno/testCookieValue");</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">return</span> <span class="hljs-string">"redirect:/param.jsp"</span>;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    }</div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<p><img alt="" class="has" height="18" src="https://img-blog.csdnimg.cn/20190808160458233.png" width="474"></p>
<h2 id="CookieValue"><a name="t37"></a>CookieValue</h2>
<blockquote>
<p>作用：<br>
用于把指定 cookie 名称的值传入控制器方法参数。<br>
属性：<br>
value：指定 cookie 的名称。<br>
required：是否必须有此 cookie。</p>
</blockquote>

<p><img alt="" class="has" height="22" src="https://img-blog.csdnimg.cn/20190808160527871.png" width="425"></p>
<p><img alt="" class="has" height="244" src="https://img-blog.csdnimg.cn/2019080816053938.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="785"></p>
<p><img alt="" class="has" height="22" src="https://img-blog.csdnimg.cn/20190808160650482.png" width="244"></p>
<h2 id="ModelAttribute"><a name="t38"></a>ModelAttribute</h2>
<blockquote>
<p>作用：<br>
该注解是 SpringMVC4.3 版本以后新加入的。它可以用于修饰方法和参数。<br>
出现在方法上，表示当前方法会在控制器的方法执行之前，先执行。它可以修饰没有返回值的方法，也可以修饰有具体返回值的方法。<br>
出现在参数上，获取指定的数据给参数赋值。<br>
属性：<br>
value：用于获取数据的 key。key 可以是 POJO 的属性名称，也可以是 map 结构的 key。<br>
应用场景：<br>
当表单提交数据不是完整的实体类数据时，保证没有提交数据的字段使用数据库对象原来的数据。<br>
例如：<br>
我们在编辑一个用户时，用户有一个创建信息字段，该字段的值是不允许被修改的。在提交表单数据是肯定没有此字段的内容，一旦更新会把该字段内容置为 null，此时就可以使用此注解解决问题。</p>
</blockquote>

<p><img alt="" class="has" height="107" src="https://img-blog.csdnimg.cn/20190808160755114.png" width="482"></p>
<p><img alt="" class="has" height="239" src="https://img-blog.csdnimg.cn/20190808160809443.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="609"></p>
<p><img alt="" class="has" height="289" src="https://img-blog.csdnimg.cn/20190808161229838.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="480"></p>
<p><img alt="" class="has" height="223" src="https://img-blog.csdnimg.cn/20190808160835408.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="537"></p>
<h2 id="SessionAttribute"><a name="t39"></a>SessionAttribute</h2>
<blockquote>
<p>作用：<br>
用于多次执行控制器方法间的参数共享。<br>
属性：<br>
value：用于指定存入的属性名称<br>
type：用于指定存入的数据类型。</p>
</blockquote>

<p><img alt="" class="has" height="64" src="https://img-blog.csdnimg.cn/2019080816141052.png" width="563"></p>
<pre class="has" name="code"><code class="hljs kotlin"><ol class="hljs-ln"><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="1"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment"><span class="hljs-comment">/**</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="2"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * SessionAttributes的注解</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="3"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     *</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="4"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@return</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="5"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     */</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="6"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-meta">@RequestMapping(value = <span class="hljs-meta-string">"/testSessionAttributes"</span>)</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="7"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-keyword">public</span> String testSessionAttributes(Model model) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="8"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(<span class="hljs-string">"testSessionAttributes..."</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="9"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-comment">// 底层会存储到request域对象中</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="10"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        model.addAttribute(<span class="hljs-string">"msg"</span>, <span class="hljs-string">"美美"</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="11"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">return</span> <span class="hljs-string">"success"</span>;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="12"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    }</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="13"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="14"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment"><span class="hljs-comment">/**</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="15"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * 获取值</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="16"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     *</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="17"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@param</span> modelMap</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="18"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@return</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="19"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     */</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="20"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-meta">@RequestMapping(value = <span class="hljs-meta-string">"/getSessionAttributes"</span>)</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="21"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-keyword">public</span> String getSessionAttributes(ModelMap modelMap) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="22"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(<span class="hljs-string">"getSessionAttributes..."</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="23"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        String msg = (String) modelMap.<span class="hljs-keyword">get</span>(<span class="hljs-string">"msg"</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="24"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(msg);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="25"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">return</span> <span class="hljs-string">"success"</span>;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="26"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    }</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="27"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"> </div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="28"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-comment"><span class="hljs-comment">/**</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="29"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * 清除</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="30"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     *</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="31"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@param</span> status</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="32"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     * <span class="hljs-doctag">@return</span></span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="33"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line"><span class="hljs-comment">     */</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="34"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-meta">@RequestMapping(value = <span class="hljs-meta-string">"/delSessionAttributes"</span>)</span></div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="35"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    <span class="hljs-keyword">public</span> String delSessionAttributes(SessionStatus status) {</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="36"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        System.<span class="hljs-keyword">out</span>.println(<span class="hljs-string">"getSessionAttributes..."</span>);</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="37"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        status.setComplete();</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="38"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">        <span class="hljs-keyword">return</span> <span class="hljs-string">"success"</span>;</div></div></li><li><div class="hljs-ln-numbers"><div class="hljs-ln-line hljs-ln-n" data-line-number="39"></div></div><div class="hljs-ln-code"><div class="hljs-ln-line">    }</div></div></li></ol></code><div class="hljs-button {2}" data-title="复制" onclick="hljs.copyCode(event)"></div></pre>
<p>success.jsp&nbsp;<img alt="" class="has" height="26" src="https://img-blog.csdnimg.cn/20190808161655376.png" width="142"></p>
<p>存入session：</p>
<p><img alt="" class="has" height="85" src="https://img-blog.csdnimg.cn/20190808162035184.png" width="646"></p>
<p><img alt="" class="has" height="44" src="https://img-blog.csdnimg.cn/20190808162144299.png" width="151"></p>
<p><img alt="" class="has" height="91" src="https://img-blog.csdnimg.cn/20190808162202435.png" width="219"></p>
