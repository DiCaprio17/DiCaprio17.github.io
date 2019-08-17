---
layout:     post
title:      Maven实战总结（IDEA）
subtitle:   Maven
date:       2019-08-18
author:     DiCaprio
header-img: img/home-bg-o.jpg
catalog: true
tags:
    - Maven
---

<p id="main-toc"><strong>目录</strong></p>


<p id="%E4%B8%80%E3%80%81%20%C2%A0%E5%9B%9E%E9%A1%BE%5B%20%E7%90%86%E8%A7%A3%5D-toc" style="margin-left:0px;"><a href="#%E4%B8%80%E3%80%81%20%C2%A0%E5%9B%9E%E9%A1%BE%5B%20%E7%90%86%E8%A7%A3%5D" rel="nofollow" data-token="508f3b3ecba02bc7c0334c76e352be4c" target="_self">一、 &nbsp;回顾[ 理解]</a></p>
<p id="1.%20Maven%20%E7%9A%84%E5%A5%BD%E5%A4%84-toc" style="margin-left:40px;"><a href="#1.%20Maven%20%E7%9A%84%E5%A5%BD%E5%A4%84" rel="nofollow" data-token="75e9c3abe44cb18c7388c22a10111d63" target="_self">1. Maven 的好处</a></p>
<p id="2.%20%E5%AE%89%E8%A3%85%E9%85%8D%E7%BD%AE%20maven-toc" style="margin-left:40px;"><a href="#2.%20%E5%AE%89%E8%A3%85%E9%85%8D%E7%BD%AE%20maven" rel="nofollow" data-token="4916689fc089e1309ddb79d19d0e36c9" target="_self">2. 安装配置 maven</a></p>
<p id="3.%20%E4%B8%89%E7%A7%8D%E4%BB%93%E5%BA%93-toc" style="margin-left:40px;"><a href="#3.%20%E4%B8%89%E7%A7%8D%E4%BB%93%E5%BA%93" rel="nofollow" data-token="35a03601fb6638f0395fff2636ebbc65" target="_self">3. 三种仓库</a></p>
<p id="4.%20%E5%B8%B8%E8%A7%81%E7%9A%84%E5%91%BD%E4%BB%A4-toc" style="margin-left:40px;"><a href="#4.%20%E5%B8%B8%E8%A7%81%E7%9A%84%E5%91%BD%E4%BB%A4" rel="nofollow" data-token="a15e23196d70ac3aa361755bc6dcdf9f" target="_self">4. 常见的命令</a></p>
<p id="5.%C2%A0%E5%9D%90%E6%A0%87%E7%9A%84%E4%B9%A6%E5%86%99%E8%A7%84%E8%8C%83-toc" style="margin-left:40px;"><a href="#5.%C2%A0%E5%9D%90%E6%A0%87%E7%9A%84%E4%B9%A6%E5%86%99%E8%A7%84%E8%8C%83" rel="nofollow" data-token="ec75ed18d46befe1ec6b3123a959f715" target="_self">5.&nbsp;坐标的书写规范</a></p>
<p id="6.%C2%A0%E5%A6%82%E4%BD%95%E6%B7%BB%E5%8A%A0%E5%9D%90%E6%A0%87-toc" style="margin-left:40px;"><a href="#6.%C2%A0%E5%A6%82%E4%BD%95%E6%B7%BB%E5%8A%A0%E5%9D%90%E6%A0%87" rel="nofollow" data-token="b862071a67e10078ace6c04a887e1e5f" target="_self">6.&nbsp;如何添加坐标</a></p>
<p id="7.%C2%A0%E4%BE%9D%E8%B5%96%E8%8C%83%E5%9B%B4-toc" style="margin-left:40px;"><a href="#7.%C2%A0%E4%BE%9D%E8%B5%96%E8%8C%83%E5%9B%B4" rel="nofollow" data-token="5af17dec372a8f716f448baf019fcf1b" target="_self">7.&nbsp;依赖范围</a></p>
<p id="%E4%BA%8C%E3%80%81maven%20%C2%A0%E6%9E%84%E5%BB%BA%20SSM%20%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D-toc" style="margin-left:0px;"><a href="#%E4%BA%8C%E3%80%81maven%20%C2%A0%E6%9E%84%E5%BB%BA%20SSM%20%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D" rel="nofollow" data-token="8c7ed5022e8e336f673f8557c7a4b568" target="_self">二、maven &nbsp;构建 SSM 工程[ 应用]</a></p>
<p id="1.%20%C2%A0%E9%9C%80%E6%B1%82-toc" style="margin-left:40px;"><a href="#1.%20%C2%A0%E9%9C%80%E6%B1%82" rel="nofollow" data-token="9b4b570f03c0779d651a925719f04927" target="_self">1. &nbsp;需求</a></p>
<p id="2.%C2%A0%E5%87%86%E5%A4%87%E6%95%B0%E6%8D%AE%E5%BA%93-toc" style="margin-left:40px;"><a href="#2.%C2%A0%E5%87%86%E5%A4%87%E6%95%B0%E6%8D%AE%E5%BA%93" rel="nofollow" data-token="bb65ed8c6e73d15c0fbe64f2f88ad69f" target="_self">2.&nbsp;准备数据库</a></p>
<p id="3.%20%C2%A0%E5%88%9B%E5%BB%BA%E4%B8%80%E4%B8%AA%20maven%C2%A0-toc" style="margin-left:40px;"><a href="#3.%20%C2%A0%E5%88%9B%E5%BB%BA%E4%B8%80%E4%B8%AA%20maven%C2%A0" rel="nofollow" data-token="5114338ec7aa0050a09c893923c9be30" target="_self">3. &nbsp;创建一个 maven&nbsp;</a></p>
<p id="1%E3%80%81%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%20ssm_maven%20%E9%A1%B9%E7%9B%AE%2C%E4%BD%BF%E7%94%A8%E4%B8%8B%E5%9B%BE%E9%80%89%E4%B8%AD%E7%9A%84%E9%AA%A8%E6%9E%B6-toc" style="margin-left:80px;"><a href="#1%E3%80%81%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%20ssm_maven%20%E9%A1%B9%E7%9B%AE%2C%E4%BD%BF%E7%94%A8%E4%B8%8B%E5%9B%BE%E9%80%89%E4%B8%AD%E7%9A%84%E9%AA%A8%E6%9E%B6" rel="nofollow" data-token="7a134f93e5cbf6a91c724247f3e2706c" target="_self">1、新建一个 ssm_maven 项目,使用下图选中的骨架</a></p>
<p id="2%E3%80%81%E5%A1%AB%E5%86%99%E5%9D%90%E6%A0%87-toc" style="margin-left:80px;"><a href="#2%E3%80%81%E5%A1%AB%E5%86%99%E5%9D%90%E6%A0%87" rel="nofollow" data-token="0a1ef3c99313aaf792be7ef66a582c91" target="_self">2、填写坐标</a></p>
<p id="3%E3%80%81%E6%9F%A5%E7%9C%8B%E6%98%AF%E5%90%A6%E4%BD%BF%E7%94%A8%E7%9A%84%E8%87%AA%E5%B7%B1%E7%9A%84%E7%A7%81%E6%9C%8D-toc" style="margin-left:80px;"><a href="#3%E3%80%81%E6%9F%A5%E7%9C%8B%E6%98%AF%E5%90%A6%E4%BD%BF%E7%94%A8%E7%9A%84%E8%87%AA%E5%B7%B1%E7%9A%84%E7%A7%81%E6%9C%8D" rel="nofollow" data-token="7b5d20b9cb0468a6295424f889100592" target="_self">3、查看是否使用的自己的私服</a></p>
<p id="5%E3%80%81%E5%9C%A8%20main%20%E7%9B%AE%E5%BD%95%E4%B8%8B%E6%96%B0%E5%BB%BA%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9-toc" style="margin-left:80px;"><a href="#5%E3%80%81%E5%9C%A8%20main%20%E7%9B%AE%E5%BD%95%E4%B8%8B%E6%96%B0%E5%BB%BA%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9" rel="nofollow" data-token="0e54888c8600b03d63e36240b14a9df1" target="_self">5、在 main 目录下新建 java 和 resources文件夹</a></p>
<p id="6%E3%80%81%E6%8A%8A%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9%E8%BD%AC%E6%88%90source%20root-toc" style="margin-left:80px;"><a href="#6%E3%80%81%E6%8A%8A%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9%E8%BD%AC%E6%88%90source%20root" rel="nofollow" data-token="8c025c4d41d741b9d6cf51101d06f3d6" target="_self">6、把 java 和 resources文件夹转成source root</a></p>
<p id="7%E3%80%81%E4%BF%AE%E6%94%B9%E7%BC%96%E8%AF%91%E7%89%88%E6%9C%AC%EF%BC%8C%E5%9C%A8%20pom.xml%20%E6%96%87%E4%BB%B6%E4%B8%AD%E6%B7%BB%E5%8A%A0-toc" style="margin-left:80px;"><a href="#7%E3%80%81%E4%BF%AE%E6%94%B9%E7%BC%96%E8%AF%91%E7%89%88%E6%9C%AC%EF%BC%8C%E5%9C%A8%20pom.xml%20%E6%96%87%E4%BB%B6%E4%B8%AD%E6%B7%BB%E5%8A%A0" rel="nofollow" data-token="90d053c4f04977d1c8065693db0ee011" target="_self">7、修改编译版本，在 pom.xml 文件中添加</a></p>
<p id="4.%C2%A0%E7%9F%A5%E8%AF%86%E7%82%B9%E5%87%86%E5%A4%87-toc" style="margin-left:40px;"><a href="#4.%C2%A0%E7%9F%A5%E8%AF%86%E7%82%B9%E5%87%86%E5%A4%87" rel="nofollow" data-token="8606eeb85ebab93aa55540be9d31142b" target="_self">4.&nbsp;知识点准备</a></p>
<p id="4.1%20%C2%A0%E4%BB%80%E4%B9%88%E6%98%AF%E4%BE%9D%E8%B5%96%E4%BC%A0%E9%80%92-toc" style="margin-left:80px;"><a href="#4.1%20%C2%A0%E4%BB%80%E4%B9%88%E6%98%AF%E4%BE%9D%E8%B5%96%E4%BC%A0%E9%80%92" rel="nofollow" data-token="2455fc42895d535f40e85e345bb3797d" target="_self">4.1 &nbsp;什么是依赖传递</a></p>
<p id="4.2%C2%A0%E4%BE%9D%E8%B5%96%E5%86%B2%E7%AA%81%E7%9A%84%E8%A7%A3%E5%86%B3-toc" style="margin-left:40px;"><a href="#4.2%C2%A0%E4%BE%9D%E8%B5%96%E5%86%B2%E7%AA%81%E7%9A%84%E8%A7%A3%E5%86%B3" rel="nofollow" data-token="69f51f01c3dc6d29f0d74257fef0337a" target="_self">4.2&nbsp;依赖冲突的解决</a></p>
<p id="4.2.1%C2%A0%E4%BE%9D%E8%B5%96%E8%B0%83%E8%A7%A3%E5%8E%9F%E5%88%99-toc" style="margin-left:80px;"><a href="#4.2.1%C2%A0%E4%BE%9D%E8%B5%96%E8%B0%83%E8%A7%A3%E5%8E%9F%E5%88%99" rel="nofollow" data-token="2f536625d003cde5e2bd01977e27adbc" target="_self">4.2.1&nbsp;依赖调解原则</a></p>
<p id="4.2.2%C2%A0%E6%8E%92%E9%99%A4%E4%BE%9D%E8%B5%96-toc" style="margin-left:80px;"><a href="#4.2.2%C2%A0%E6%8E%92%E9%99%A4%E4%BE%9D%E8%B5%96" rel="nofollow" data-token="2077bdc1cefe0fa30d58c729cd13c4ad" target="_self">4.2.2&nbsp;排除依赖</a></p>
<p id="4.2.3%C2%A0%E9%94%81%E5%AE%9A%E7%89%88%E6%9C%AC-toc" style="margin-left:80px;"><a href="#4.2.3%C2%A0%E9%94%81%E5%AE%9A%E7%89%88%E6%9C%AC" rel="nofollow" data-token="955ccce0883d5946cdb8c3ca178e4631" target="_self">4.2.3&nbsp;锁定版本</a></p>
<p id="5.%C2%A0%E5%AE%9A%E4%B9%89%20pom.xml-toc" style="margin-left:40px;"><a href="#5.%C2%A0%E5%AE%9A%E4%B9%89%20pom.xml" rel="nofollow" data-token="ad3daed9c93871cde50f642a842ee8e9" target="_self">5.&nbsp;定义 pom.xml</a></p>
<p id="6.%20Dao%20%E5%B1%82-toc" style="margin-left:40px;"><a href="#6.%20Dao%20%E5%B1%82" rel="nofollow" data-token="342bd60e4a664afc75b185bc6e0a7716" target="_self">6. Dao 层</a></p>
<p id="6.1%20pojo%C2%A0-toc" style="margin-left:80px;"><a href="#6.1%20pojo%C2%A0" rel="nofollow" data-token="fca1551b6a2884f84379fe9ab636d19f" target="_self">6.1 pojo&nbsp;</a></p>
<p id="6.2%20dao%20%E5%B1%82%E4%BB%A3%E7%A0%81-toc" style="margin-left:80px;"><a href="#6.2%20dao%20%E5%B1%82%E4%BB%A3%E7%A0%81" rel="nofollow" data-token="9682dd3e3e028530105fc37821fe8e48" target="_self">6.2 dao 层代码</a></p>
<p id="6.3%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6-toc" style="margin-left:80px;"><a href="#6.3%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6" rel="nofollow" data-token="a2bd033ad60220b73e54a8a902ad164f" target="_self">6.3 &nbsp;配置文件</a></p>
<p id="6.4%20%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95-toc" style="margin-left:80px;"><a href="#6.4%20%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95" rel="nofollow" data-token="efba352ef45ede1a10fba447dabc3236" target="_self">6.4 单元测试</a></p>
<p id="7.%20%C2%A0Service%20%E5%B1%82-toc" style="margin-left:40px;"><a href="#7.%20%C2%A0Service%20%E5%B1%82" rel="nofollow" data-token="e4f33b33462894f4e5c26c5190fb7718" target="_self">7. &nbsp;Service 层</a></p>
<p id="7.1%20%E4%BB%A3%E7%A0%81-toc" style="margin-left:80px;"><a href="#7.1%20%E4%BB%A3%E7%A0%81" rel="nofollow" data-token="51088f773b72c2137f40ed2e883db819" target="_self">7.1 代码</a></p>
<p id="7.2%20%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6-toc" style="margin-left:80px;"><a href="#7.2%20%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6" rel="nofollow" data-token="78bd4b4c0b51def8c34ae4acd530260f" target="_self">7.2 配置文件</a></p>
<p id="8.%20%C2%A0Web%20%E5%B1%82-toc" style="margin-left:40px;"><a href="#8.%20%C2%A0Web%20%E5%B1%82" rel="nofollow" data-token="55a20d7f99756326b09400cc981004c9" target="_self">8. &nbsp;Web 层</a></p>
<p id="8.2%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6-toc" style="margin-left:80px;"><a href="#8.2%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6" rel="nofollow" data-token="e906624d65a4c7bbd610611a89d16e8b" target="_self">8.2 &nbsp;配置文件</a></p>
<p id="9.%20%C2%A0Jsp-toc" style="margin-left:40px;"><a href="#9.%20%C2%A0Jsp" rel="nofollow" data-token="29c3078eca14235052947654f6d186bf" target="_self">9. &nbsp;Jsp</a></p>
<p id="10.%20%C2%A0%E8%BF%90%E8%A1%8C%20%E4%B8%8E%E8%B0%83%E8%AF%95-toc" style="margin-left:40px;"><a href="#10.%20%C2%A0%E8%BF%90%E8%A1%8C%20%E4%B8%8E%E8%B0%83%E8%AF%95" rel="nofollow" data-token="3d3eaee0eb48d27bc074e807c54652ed" target="_self">10. &nbsp;运行 与调试</a></p>
<p id="%E4%B8%89%E3%80%81%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D-toc" style="margin-left:0px;"><a href="#%E4%B8%89%E3%80%81%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D" rel="nofollow" data-token="bfb74b5a571ecb99f1c8eac02beae9f1" target="_self">三、 &nbsp;分模块构建工程[ 应用]</a></p>
<p style="margin-left:40px;"><a href="#1.%20%C2%A0%E9%9C%80%E6%B1%82" rel="nofollow" data-token="9b4b570f03c0779d651a925719f04927" target="_self">1. &nbsp;需求</a></p>
<p id="%E9%9C%80%E6%B1%82%E6%8F%8F%E8%BF%B0-toc" style="margin-left:80px;"><a href="#%E9%9C%80%E6%B1%82%E6%8F%8F%E8%BF%B0" rel="nofollow" data-token="6c5818d511eb418658860b05ca880d57" target="_self">需求描述</a></p>
<p id="%E7%90%86%E8%A7%A3%20%E7%BB%A7%E6%89%BF%E5%92%8C%E8%81%9A%E5%90%88-toc" style="margin-left:80px;"><a href="#%E7%90%86%E8%A7%A3%20%E7%BB%A7%E6%89%BF%E5%92%8C%E8%81%9A%E5%90%88" rel="nofollow" data-token="bdab4a93ed42855ca0d06b6b9517a1d4" target="_self">理解 继承和聚合</a></p>
<p id="2.%20%C2%A0%E6%A1%88%E4%BE%8B%E5%AE%9E%E7%8E%B0-toc" style="margin-left:40px;"><a href="#2.%20%C2%A0%E6%A1%88%E4%BE%8B%E5%AE%9E%E7%8E%B0" rel="nofollow" data-token="dd5f30bbe83c63dfdbaaaa26d599a21f" target="_self">2. &nbsp;案例实现</a></p>
<p id="2.1%20maven-parent%20%C2%A0%E7%88%B6%E6%A8%A1%E5%9D%97-toc" style="margin-left:80px;"><a href="#2.1%20maven-parent%20%C2%A0%E7%88%B6%E6%A8%A1%E5%9D%97" rel="nofollow" data-token="c1c249f15f062f114f74caa0456755a0" target="_self">2.1 maven-parent &nbsp;父模块</a></p>
<p id="2.2%20ssm_dao%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97-toc" style="margin-left:80px;"><a href="#2.2%20ssm_dao%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97" rel="nofollow" data-token="ec47488c980981b23019be3c1fbc7abb" target="_self">2.2 ssm_dao &nbsp;子模块</a></p>
<p id="2.3%20ssm_service%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97.-toc" style="margin-left:80px;"><a href="#2.3%20ssm_service%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97." rel="nofollow" data-token="2b02642e84b16eb284f06bca51e74b12" target="_self">2.3 ssm_service &nbsp;子模块.</a></p>
<p id="2.4%20ssm_web%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97-toc" style="margin-left:80px;"><a href="#2.4%20ssm_web%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97" rel="nofollow" data-token="f538e3b36b4cac293b2762e1cbb02dea" target="_self">2.4 ssm_web &nbsp;子模块</a></p>
<p id="2.5%20%C2%A0%E8%BF%90%E8%A1%8C%20%E8%B0%83%E8%AF%95-toc" style="margin-left:80px;"><a href="#2.5%20%C2%A0%E8%BF%90%E8%A1%8C%20%E8%B0%83%E8%AF%95" rel="nofollow" data-token="a99ee95d0408baa38d27e2dac2af3abc" target="_self">2.5 &nbsp;运行 调试</a></p>
<p id="3.%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B--%20%E4%BE%9D%E8%B5%96%E6%95%B4%E5%90%88-toc" style="margin-left:40px;"><a href="#3.%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B--%20%E4%BE%9D%E8%B5%96%E6%95%B4%E5%90%88" rel="nofollow" data-token="64a38f9d367373ef1da09ad3b5c0bbc9" target="_self">3. &nbsp;分模块构建工程-- 依赖整合</a></p>
<p id="%E5%9B%9B%E3%80%81%20maven%20%C2%A0%E7%A7%81%E6%9C%8D%5B%20%E4%BA%86%E8%A7%A3%5D-toc" style="margin-left:0px;"><a href="#%E5%9B%9B%E3%80%81%20maven%20%C2%A0%E7%A7%81%E6%9C%8D%5B%20%E4%BA%86%E8%A7%A3%5D" rel="nofollow" data-token="68e5609c63835b2b03fc8649271dc4c2" target="_self">四、 maven &nbsp;私服[ 了解]</a></p>
<p style="margin-left:40px;"><a href="#1.%20%C2%A0%E9%9C%80%E6%B1%82" rel="nofollow" data-token="9b4b570f03c0779d651a925719f04927" target="_self">1. &nbsp;需求</a></p>
<p id="2.%20%C2%A0%E5%88%86%E6%9E%90-toc" style="margin-left:40px;"><a href="#2.%20%C2%A0%E5%88%86%E6%9E%90" rel="nofollow" data-token="42735b0b4b737948c3e9b70ecb0906b4" target="_self">2. &nbsp;分析</a></p>
<p id="3.%C2%A0%E6%90%AD%E5%BB%BA%E7%A7%81%E6%9C%8D%E7%8E%AF%E5%A2%83-toc" style="margin-left:40px;"><a href="#3.%C2%A0%E6%90%AD%E5%BB%BA%E7%A7%81%E6%9C%8D%E7%8E%AF%E5%A2%83" rel="nofollow" data-token="4df78fa54f5c5e8c45e5cfa737cc3fa7" target="_self">3.&nbsp;搭建私服环境</a></p>
<p id="3.1%20%C2%A0%E4%B8%8B%E8%BD%BD%20nexus-toc" style="margin-left:80px;"><a href="#3.1%20%C2%A0%E4%B8%8B%E8%BD%BD%20nexus" rel="nofollow" data-token="71a72ebdb8b6196218f73474ef394a32" target="_self">3.1 &nbsp;下载 nexus</a></p>
<p id="3.2%20%C2%A0%E5%AE%89%E8%A3%85%20nexus-toc" style="margin-left:80px;"><a href="#3.2%20%C2%A0%E5%AE%89%E8%A3%85%20nexus" rel="nofollow" data-token="e2d2dfc191a36155611dd60af95af9f3" target="_self">3.2 &nbsp;安装 nexus</a></p>
<p id="3.3%20%C2%A0%E5%8D%B8%E8%BD%BD%20nexus-toc" style="margin-left:80px;"><a href="#3.3%20%C2%A0%E5%8D%B8%E8%BD%BD%20nexus" rel="nofollow" data-token="034f1dcd19a9b991b3ecb25aab023ffa" target="_self">3.3 &nbsp;卸载 nexus</a></p>
<p id="3.4%20%C2%A0%E5%90%AF%E5%8A%A8%20nexus-toc" style="margin-left:80px;"><a href="#3.4%20%C2%A0%E5%90%AF%E5%8A%A8%20nexus" rel="nofollow" data-token="bacc6fd4b67cc32e3d5eb1c785b351c5" target="_self">3.4 &nbsp;启动 nexus</a></p>
<p id="3.5%20%E4%BB%93%E5%BA%93%E7%B1%BB%E5%9E%8B-toc" style="margin-left:80px;"><a href="#3.5%20%E4%BB%93%E5%BA%93%E7%B1%BB%E5%9E%8B" rel="nofollow" data-token="f088d9ff2753237e6586e2985a33b6d3" target="_self">3.5 仓库类型</a></p>
<p id="4.%20%C2%A0%E5%B0%86%E9%A1%B9%E7%9B%AE%E5%8F%91%E5%B8%83%E5%88%B0%E7%A7%81%E6%9C%8D-toc" style="margin-left:40px;"><a href="#4.%20%C2%A0%E5%B0%86%E9%A1%B9%E7%9B%AE%E5%8F%91%E5%B8%83%E5%88%B0%E7%A7%81%E6%9C%8D" rel="nofollow" data-token="bfdc7e645e45d69bc4f1d747037d13e5" target="_self">4. &nbsp;将项目发布到私服</a></p>
<p id="4.1%20%E9%9C%80%E6%B1%82-toc" style="margin-left:80px;"><a href="#4.1%20%E9%9C%80%E6%B1%82" rel="nofollow" data-token="7c08021878b0cd78657f04eea57bd7ea" target="_self">4.1 需求</a></p>
<p id="4.3%20%C2%A0%E6%B5%8B%E8%AF%95-toc" style="margin-left:80px;"><a href="#4.3%20%C2%A0%E6%B5%8B%E8%AF%95" rel="nofollow" data-token="9eff069688043e8ff4a013bcbb75387c" target="_self">4.3 &nbsp;测试</a></p>
<p id="5.%20%C2%A0%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85-toc" style="margin-left:40px;"><a href="#5.%20%C2%A0%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85" rel="nofollow" data-token="fbd6cc6e611b71c33870a0faf322c5e6" target="_self">5. &nbsp;从私服下载 jar 包</a></p>
<p id="5.1%20%C2%A0%E9%9C%80%E6%B1%82-toc" style="margin-left:80px;"><a href="#5.1%20%C2%A0%E9%9C%80%E6%B1%82" rel="nofollow" data-token="221679f08cae0bfe2d5d78e51eb3d5de" target="_self">5.1 &nbsp;需求</a></p>
<p id="5.2%20%C2%A0%E7%AE%A1%E7%90%86%E4%BB%93%E5%BA%93%E7%BB%84-toc" style="margin-left:80px;"><a href="#5.2%20%C2%A0%E7%AE%A1%E7%90%86%E4%BB%93%E5%BA%93%E7%BB%84" rel="nofollow" data-token="ec1121e8aeed4e1c330648daca963e7d" target="_self">5.2 &nbsp;管理仓库组</a></p>
<p id="5.3%20%E5%9C%A8%20setting.xml%20%C2%A0%E4%B8%AD%E9%85%8D%E7%BD%AE%E4%BB%93%E5%BA%93-toc" style="margin-left:80px;"><a href="#5.3%20%E5%9C%A8%20setting.xml%20%C2%A0%E4%B8%AD%E9%85%8D%E7%BD%AE%E4%BB%93%E5%BA%93" rel="nofollow" data-token="de163f8447508bb4c38473daeb98d0a8" target="_self">5.3 在 setting.xml &nbsp;中配置仓库</a></p>
<p id="5.4%20%C2%A0%E6%B5%8B%E8%AF%95%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85-toc" style="margin-left:80px;"><a href="#5.4%20%C2%A0%E6%B5%8B%E8%AF%95%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85" rel="nofollow" data-token="2d9fa37d4285931d91925b9fe08a7761" target="_self">5.4 &nbsp;测试从私服下载 jar 包</a></p>
<p id="%E4%BA%94%E3%80%81%20%C2%A0%E6%8A%8A%E7%AC%AC%E4%B8%89%E6%96%B9%20jar%20%C2%A0%E5%8C%85%E6%94%BE%E5%85%A5%E6%9C%AC%E5%9C%B0%E4%BB%93%E5%BA%93%E6%88%96%E7%A7%81%E6%9C%8D-toc" style="margin-left:0px;"><a href="#%E4%BA%94%E3%80%81%20%C2%A0%E6%8A%8A%E7%AC%AC%E4%B8%89%E6%96%B9%20jar%20%C2%A0%E5%8C%85%E6%94%BE%E5%85%A5%E6%9C%AC%E5%9C%B0%E4%BB%93%E5%BA%93%E6%88%96%E7%A7%81%E6%9C%8D" rel="nofollow" data-token="57d2dbb4918b2dff471e55f2a85a18a3" target="_self">五、 &nbsp;把第三方 jar &nbsp;包放入本地仓库或私服</a></p>
<p id="1.%20%C2%A0%E5%AF%BC%E5%85%A5%E6%9C%AC%E5%9C%B0%E5%BA%93-toc" style="margin-left:40px;"><a href="#1.%20%C2%A0%E5%AF%BC%E5%85%A5%E6%9C%AC%E5%9C%B0%E5%BA%93" rel="nofollow" data-token="6fc7380939c31ac68202dd39fa573585" target="_self">1. &nbsp;导入本地库</a></p>
<p id="2.%20%E5%AF%BC%E5%85%A5%E7%A7%81%E6%9C%8D-toc" style="margin-left:40px;"><a href="#2.%20%E5%AF%BC%E5%85%A5%E7%A7%81%E6%9C%8D" rel="nofollow" data-token="a4023a18b156976cd22988a517ae22d3" target="_self">2. 导入私服</a></p>
<p id="3.%20%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E-toc" style="margin-left:40px;"><a href="#3.%20%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E" rel="nofollow" data-token="67225ce2e1bd56af19e465f58c57c232" target="_self">3. 参数说明</a></p>
<hr id="hr-toc"><h1 id="%E4%B8%80%E3%80%81%20%C2%A0%E5%9B%9E%E9%A1%BE%5B%20%E7%90%86%E8%A7%A3%5D"><a name="t0"></a>一、 &nbsp;回顾[ 理解]</h1>

<h2 id="1.%20Maven%20%E7%9A%84%E5%A5%BD%E5%A4%84"><a name="t1"></a>1. Maven 的好处</h2>
<blockquote>
<p>节省磁盘空间<br>
可以一键构建<br>
可以跨平台<br>
应用在大型项目时可以提高开发效率</p>
</blockquote>

<h2 id="2.%20%E5%AE%89%E8%A3%85%E9%85%8D%E7%BD%AE%20maven"><a name="t2"></a>2. 安装配置 maven</h2>
<p>注意：3.3+版本需要 jdkj.7+以上的支持</p>
<h2 id="3.%20%E4%B8%89%E7%A7%8D%E4%BB%93%E5%BA%93"><a name="t3"></a>3. 三种仓库</h2>
<blockquote>
<p>本地仓库<br>
远程仓库（私服）<br>
中央仓库</p>
</blockquote>

<h2 id="4.%20%E5%B8%B8%E8%A7%81%E7%9A%84%E5%91%BD%E4%BB%A4"><a name="t4"></a>4. 常见的命令</h2>
<blockquote>
<p>Compile<br>
Test<br>
Package<br>
Install<br>
Deploy<br>
Clean</p>
</blockquote>

<h2 id="5.%C2%A0%E5%9D%90%E6%A0%87%E7%9A%84%E4%B9%A6%E5%86%99%E8%A7%84%E8%8C%83"><a name="t5"></a>5.&nbsp;坐标的书写规范</h2>
<blockquote>
<p>groupId 公司或组织域名的倒序<br>
artifactId 项目名或模块名<br>
version 版本号</p>
</blockquote>

<h2 id="6.%C2%A0%E5%A6%82%E4%BD%95%E6%B7%BB%E5%8A%A0%E5%9D%90%E6%A0%87"><a name="t6"></a>6.&nbsp;如何添加坐标</h2>
<blockquote>
<p>1、在本地仓库中搜索<br>
2、互联网上搜，推荐网址 http://www.mvnrepository.com/</p>
</blockquote>

<h2 id="7.%C2%A0%E4%BE%9D%E8%B5%96%E8%8C%83%E5%9B%B4"><a name="t7"></a>7.&nbsp;依赖范围</h2>
<blockquote>
<p>Compile<br>
Test<br>
Runtime<br>
Provided</p>
</blockquote>

<h1 id="%E4%BA%8C%E3%80%81maven%20%C2%A0%E6%9E%84%E5%BB%BA%20SSM%20%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D"><a name="t8"></a>二、maven &nbsp;构建 SSM 工程[ 应用]</h1>
<h2 id="1.%20%C2%A0%E9%9C%80%E6%B1%82"><a name="t9"></a>1. &nbsp;需求</h2>
<p>实现 SSM 工程构建，规范依赖管理。场景：根据 id展示商品信息</p>
<h2 id="2.%C2%A0%E5%87%86%E5%A4%87%E6%95%B0%E6%8D%AE%E5%BA%93"><a name="t10"></a>2.&nbsp;准备数据库</h2>
<p><img alt="" class="has" height="34" src="https://img-blog.csdnimg.cn/20190817125453348.png" width="188"></p>
<h2 id="3.%20%C2%A0%E5%88%9B%E5%BB%BA%E4%B8%80%E4%B8%AA%20maven%C2%A0"><a name="t11"></a>3. &nbsp;创建一个 maven&nbsp;</h2>
<h3 id="1%E3%80%81%E6%96%B0%E5%BB%BA%E4%B8%80%E4%B8%AA%20ssm_maven%20%E9%A1%B9%E7%9B%AE%2C%E4%BD%BF%E7%94%A8%E4%B8%8B%E5%9B%BE%E9%80%89%E4%B8%AD%E7%9A%84%E9%AA%A8%E6%9E%B6"><a name="t12"></a>1、新建一个 ssm_maven 项目,使用下图选中的骨架</h3>
<p><img alt="" class="has" height="423" src="https://img-blog.csdnimg.cn/20190817125528906.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="544"></p>
<h3 id="2%E3%80%81%E5%A1%AB%E5%86%99%E5%9D%90%E6%A0%87"><a name="t13"></a>2、填写坐标</h3>
<p><img alt="" class="has" height="631" src="https://img-blog.csdnimg.cn/20190817125617454.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="808"></p>
<h3 id="3%E3%80%81%E6%9F%A5%E7%9C%8B%E6%98%AF%E5%90%A6%E4%BD%BF%E7%94%A8%E7%9A%84%E8%87%AA%E5%B7%B1%E7%9A%84%E7%A7%81%E6%9C%8D"><a name="t14"></a>3、查看是否使用的自己的私服</h3>
<p><img alt="" class="has" height="653" src="https://img-blog.csdnimg.cn/20190817125605223.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="831"></p>
<h3 id="5%E3%80%81%E5%9C%A8%20main%20%E7%9B%AE%E5%BD%95%E4%B8%8B%E6%96%B0%E5%BB%BA%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9"><a name="t15"></a>5、在 main 目录下新建 java 和 resources文件夹</h3>
<p><img alt="" class="has" height="308" src="https://img-blog.csdnimg.cn/20190817125648486.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="822"></p>
<h3 id="6%E3%80%81%E6%8A%8A%20java%20%E5%92%8C%20resources%E6%96%87%E4%BB%B6%E5%A4%B9%E8%BD%AC%E6%88%90source%20root"><a name="t16"></a>6、把 java 和 resources文件夹转成source root</h3>
<p><img alt="" class="has" height="640" src="https://img-blog.csdnimg.cn/20190817125702338.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="821"></p>
<h3 id="7%E3%80%81%E4%BF%AE%E6%94%B9%E7%BC%96%E8%AF%91%E7%89%88%E6%9C%AC%EF%BC%8C%E5%9C%A8%20pom.xml%20%E6%96%87%E4%BB%B6%E4%B8%AD%E6%B7%BB%E5%8A%A0"><a name="t17"></a>7、修改编译版本，在 pom.xml 文件中添加</h3>
<p><img alt="" class="has" height="370" src="https://img-blog.csdnimg.cn/20190817125715723.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="697"></p>
<h2 id="4.%C2%A0%E7%9F%A5%E8%AF%86%E7%82%B9%E5%87%86%E5%A4%87"><a name="t18"></a>4.&nbsp;知识点准备</h2>
<h3 id="4.1%20%C2%A0%E4%BB%80%E4%B9%88%E6%98%AF%E4%BE%9D%E8%B5%96%E4%BC%A0%E9%80%92"><a name="t19"></a>4.1 &nbsp;什么是依赖传递</h3>
<p>先添加 springmvc的核心依赖的坐标</p>
<p><img alt="" class="has" height="171" src="https://img-blog.csdnimg.cn/20190817125751810.png" width="495"></p>
<blockquote>
<p>会发现出现除了 spring-webmvc 以外的其他 jar。因为我们的项目依赖 spring-webmv.jar，而<u>spring-webmv.jar 会依赖spring-beans.jar</u> 等等，所以 spring-beans.jar 这些 jar 包也出现在了我们的 maven 工程中，这种现象我们称为依赖传递。从下图中可看到他们的关系：（请注意spring-beans 的版本）</p>
</blockquote>

<p><img alt="" class="has" height="663" src="https://img-blog.csdnimg.cn/20190817125927822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="636"></p>
<h2 id="4.2%C2%A0%E4%BE%9D%E8%B5%96%E5%86%B2%E7%AA%81%E7%9A%84%E8%A7%A3%E5%86%B3"><a name="t20"></a>4.2&nbsp;依赖冲突的解决</h2>
<p>接着添加一个依赖</p>
<p><img alt="" class="has" height="265" src="https://img-blog.csdnimg.cn/20190817125953882.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="485"></p>
<blockquote>
<p>我们会发现这两个 jar 包同时都依赖了 spring-beans</p>
</blockquote>

<blockquote>
<p>但是spring-webmvc 依赖 spirng-beans-4.2.4，spring-context 依赖 spring-beans-5.0.2，但是发现<br>
spirng-beans-4.2.4 加入到工程中</p>
</blockquote>

<blockquote>
<p>而我们希望 spring-beans-5.0.2 加入工程。这就造成了依赖冲突。解决依赖冲突有以下原则：</p>
</blockquote>

<h3 id="4.2.1%C2%A0%E4%BE%9D%E8%B5%96%E8%B0%83%E8%A7%A3%E5%8E%9F%E5%88%99"><a name="t21"></a>4.2.1&nbsp;依赖调解原则</h3>
<p>maven 自动按照下边的原则调解：</p>
<p><strong>1 、第一声明者优先原则</strong><br>
在 pom 文件定义依赖，先声明的依赖为准。<br>
测试：<br>
如果将上边 spring-webmvc 和 spring-context 顺序颠倒，系统将导入 spring-beans-5.0.2。<br>
分析：<br>
由于 spring-webmvc 在前边以 spring-webmvc 依赖的 spring-beans-5.0.2 为准，所以最终spring-beans-5.0.2 添加到了工程中。</p>

<p><strong>2、路径近者优先原则</strong></p>
<blockquote>
<p>例如：还是上述情况，spring-contex 和 spring-webmvc 都会传递过来 spirng-beans，那如果直接把 spring-beans 的依赖直接写到 pom 文件中，那么项目就不会再使用其他依赖传递来的 spring-beans，因为自己直接在 pom 中定义 spring-beans要比其他依赖传递过来的路径要近。</p>
</blockquote>

<p>在本工程中的 pom 中加入 spirng-beans-5.0.2 的依赖，根据路径近者优先原则，系统将导入spirng-beans-5.0.2：</p>
<p><img alt="" class="has" height="485" src="https://img-blog.csdnimg.cn/20190817133031209.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="646"></p>
<h3 id="4.2.2%C2%A0%E6%8E%92%E9%99%A4%E4%BE%9D%E8%B5%96"><a name="t22"></a>4.2.2&nbsp;排除依赖</h3>
<blockquote>
<p>上边的问题也可以通过排除依赖方法辅助依赖调解，如下：<br>
比如在依赖 spring-webmvc 的设置中添加排除依赖，排除 spring-beans，<br>
下边的配置表示：依赖 spring-webmvc，但排除 spring-webmvc 所依赖的 spring-beans。</p>
</blockquote>

<p><img alt="" class="has" height="440" src="https://img-blog.csdnimg.cn/20190817133107564.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="592"></p>
<h3 id="4.2.3%C2%A0%E9%94%81%E5%AE%9A%E7%89%88%E6%9C%AC"><a name="t23"></a>4.2.3&nbsp;锁定版本</h3>
<blockquote>
<p>面对众多的依赖，有一种方法不用考虑依赖路径、声明优化等因素可以采用直接锁定版本的方法确定依赖构件的版本，版本锁定后则不考虑依赖的声明顺序或依赖的路径，以锁定的版本的为准添加到工程中，此方法在企业开发中常用。<br>
如下的配置是锁定了 spring-beans 和 spring-context 的版本：</p>
</blockquote>

<p><img alt="" class="has" height="336" src="https://img-blog.csdnimg.cn/20190817133222462.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="552"></p>
<blockquote>
<p>还可以把版本号提取出来，使用&lt;properties&gt;标签设置成变量</p>
</blockquote>

<p><img alt="" class="has" height="499" src="https://img-blog.csdnimg.cn/20190817133248900.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="630"></p>
<blockquote>
<p>注意：在工程中锁定依赖的版本并不代表在工程中添加了依赖，如果工程需要添加锁定版本的依赖则需要单独添加&lt;dependencies&gt;&lt;/dependencies&gt;标签，如下：</p>
</blockquote>

<p><img alt="" class="has" height="283" src="https://img-blog.csdnimg.cn/20190817133322284.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="619"></p>
<h2 id="5.%C2%A0%E5%AE%9A%E4%B9%89%20pom.xml"><a name="t24"></a>5.&nbsp;定义 pom.xml</h2>
<blockquote>
<p>maven 工程首先要识别依赖，web 工程实现 SSM 整合，需要依赖 spring-webmvc5.0.2、<br>
spring5.0.2、mybatis3.4.5等，在 pom.xml 添加工程如下依赖：<br>
（在实际企业开发中会有架构师专门来编写 pom.xml）<br>
分两步：</p>

<p>1）锁定依赖版本<br>
2）添加依赖</p>
</blockquote>

<p><img alt="" class="has" height="486" src="https://img-blog.csdnimg.cn/201908171345162.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="774"><img alt="" class="has" height="718" src="https://img-blog.csdnimg.cn/20190817134526868.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="778"><img alt="" class="has" height="531" src="https://img-blog.csdnimg.cn/20190817134547607.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="779"><img alt="" class="has" height="686" src="https://img-blog.csdnimg.cn/20190817134558969.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="776"><img alt="" class="has" height="612" src="https://img-blog.csdnimg.cn/20190817134712169.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="777"><img alt="" class="has" height="674" src="https://img-blog.csdnimg.cn/201908171347251.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="781"><img alt="" class="has" height="632" src="https://img-blog.csdnimg.cn/20190817134748414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"><img alt="" class="has" height="606" src="https://img-blog.csdnimg.cn/20190817134813807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"><img alt="" class="has" height="685" src="https://img-blog.csdnimg.cn/20190817134826751.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="775"><img alt="" class="has" height="583" src="https://img-blog.csdnimg.cn/20190817134836655.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="778"><img alt="" class="has" height="107" src="https://img-blog.csdnimg.cn/2019081713484634.png" width="782"></p>
<h2 id="6.%20Dao%20%E5%B1%82"><a name="t25"></a>6. Dao 层</h2>
<h3 id="6.1%20pojo%C2%A0"><a name="t26"></a>6.1 pojo&nbsp;</h3>
<p><img alt="" class="has" height="487" src="https://img-blog.csdnimg.cn/20190817135006257.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="768"></p>
<h3 id="6.2%20dao%20%E5%B1%82%E4%BB%A3%E7%A0%81"><a name="t27"></a>6.2 dao 层代码</h3>
<p><img alt="" class="has" height="279" src="https://img-blog.csdnimg.cn/20190817135030647.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="753"></p>
<h3 id="6.3%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6"><a name="t28"></a>6.3 &nbsp;配置文件</h3>
<p><img alt="" class="has" height="250" src="https://img-blog.csdnimg.cn/20190817135044377.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="812"></p>
<p><img alt="" class="has" height="261" src="https://img-blog.csdnimg.cn/2019081713505871.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"><img alt="" class="has" height="638" src="https://img-blog.csdnimg.cn/20190817135110894.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"><img alt="" class="has" height="162" src="https://img-blog.csdnimg.cn/20190817135126226.png" width="781"></p>
<p><img alt="" class="has" height="395" src="https://img-blog.csdnimg.cn/20190817135229154.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="785"></p>
<h3 id="6.4%20%E5%8D%95%E5%85%83%E6%B5%8B%E8%AF%95"><a name="t29"></a>6.4 单元测试</h3>
<p><img alt="" class="has" height="388" src="https://img-blog.csdnimg.cn/20190817135255521.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="781"></p>
<h2 id="7.%20%C2%A0Service%20%E5%B1%82"><a name="t30"></a>7. &nbsp;Service 层</h2>
<h3 id="7.1%20%E4%BB%A3%E7%A0%81"><a name="t31"></a>7.1 代码</h3>
<p><img alt="" class="has" height="289" src="https://img-blog.csdnimg.cn/20190817135324814.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"></p>
<h3 id="7.2%20%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6"><a name="t32"></a>7.2 配置文件</h3>
<p><img alt="" class="has" height="60" src="https://img-blog.csdnimg.cn/20190817135340290.png" width="790"></p>
<h2 id="8.%20%C2%A0Web%20%E5%B1%82"><a name="t33"></a>8. &nbsp;Web 层</h2>
<p>8.1 代码</p>
<p><img alt="" class="has" height="372" src="https://img-blog.csdnimg.cn/20190817135404196.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"></p>
<h3 id="8.2%20%C2%A0%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6"><a name="t34"></a>8.2 &nbsp;配置文件</h3>
<p>springmvc.xml</p>
<p><img alt="" class="has" height="440" src="https://img-blog.csdnimg.cn/20190817135435203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="781"><img alt="" class="has" height="106" src="https://img-blog.csdnimg.cn/20190817135441112.png" width="777"></p>
<p>Web.xml<br>
加载 spring容器，配置 springmvc前端控制器</p>

<p><img alt="" class="has" height="738" src="https://img-blog.csdnimg.cn/20190817135500929.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"></p>
<h2 id="9.%20%C2%A0Jsp"><a name="t35"></a>9. &nbsp;Jsp</h2>
<p>/WEB-INF/jsp/viewItem.jsp 如下：</p>
<p><img alt="" class="has" height="67" src="https://img-blog.csdnimg.cn/20190817135520797.png" width="780"><img alt="" class="has" height="770" src="https://img-blog.csdnimg.cn/20190817135531576.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="777"></p>
<h2 id="10.%20%C2%A0%E8%BF%90%E8%A1%8C%20%E4%B8%8E%E8%B0%83%E8%AF%95"><a name="t36"></a>10. &nbsp;运行 与调试</h2>
<p>添加 tomcat7插件，双击右侧tomcat7 运行</p>
<p><img alt="" class="has" height="378" src="https://img-blog.csdnimg.cn/2019081713560169.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="897"></p>
<p><img alt="" class="has" height="231" src="https://img-blog.csdnimg.cn/20190817135615327.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="797"></p>
<h1 id="%E4%B8%89%E3%80%81%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B%5B%20%E5%BA%94%E7%94%A8%5D"><a name="t37"></a>三、 &nbsp;分模块构建工程[ 应用]</h1>
<blockquote>
<p>基于上边的三个工程分析<br>
继承：创建一个 parent 工程将所需的依赖都配置在 pom 中<br>
聚合：聚合多个模块运行。</p>
</blockquote>

<h2><a name="t38"></a>1. &nbsp;需求</h2>
<h3 id="%E9%9C%80%E6%B1%82%E6%8F%8F%E8%BF%B0"><a name="t39"></a>需求描述</h3>
<p>将 SSM 工程拆分为多个模块开发：</p>
<p><img alt="" class="has" height="538" src="https://img-blog.csdnimg.cn/2019081713571128.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="762"></p>
<h3 id="%E7%90%86%E8%A7%A3%20%E7%BB%A7%E6%89%BF%E5%92%8C%E8%81%9A%E5%90%88"><a name="t40"></a>理解 继承和聚合</h3>
<blockquote>
<p>通常继承和聚合同时使用。<br>
&nbsp; 何为继承？<br>
继承是为了<strong>消除重复</strong>，如果将 dao、service、web 分开创建独立的工程则每个工程的 pom.xml文件中的内容存在重复，比如：设置编译版本、锁定 spring的版本的等，可以将这些重复的配置提取出来在父工程的 pom.xml 中定义。<br>
&nbsp; 何为聚合？<br>
项目开发通常是分组分模块开发，每个模块开发完成要运行整个工程需要将每个模块聚合在一起运行，比如：dao、service、web 三个工程最终会打一个独立的<strong>war</strong> 运行。</p>
</blockquote>

<h2 id="2.%20%C2%A0%E6%A1%88%E4%BE%8B%E5%AE%9E%E7%8E%B0"><a name="t41"></a>2. &nbsp;案例实现</h2>
<h3 id="2.1%20maven-parent%20%C2%A0%E7%88%B6%E6%A8%A1%E5%9D%97"><a name="t42"></a>2.1 maven-parent &nbsp;父模块</h3>
<p><strong>2.1.1 &nbsp;创建父工程</strong></p>
<p>1、选择骨架创建父工程</p>
<p><img alt="" class="has" height="590" src="https://img-blog.csdnimg.cn/2019081713584262.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="762"></p>
<p>2、填写坐标</p>
<p><img alt="" class="has" height="129" src="https://img-blog.csdnimg.cn/20190817135855598.png" width="370"></p>
<p>3、确认使用的是本地仓库</p>
<p><img alt="" class="has" height="311" src="https://img-blog.csdnimg.cn/20190817135903948.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="774"></p>
<p>4、注意代码所在的路径（默认）</p>
<p><img alt="" class="has" height="113" src="https://img-blog.csdnimg.cn/20190817135923647.png" width="768"></p>
<p>5、设置项目的打包方式</p>
<p><img alt="" class="has" height="298" src="https://img-blog.csdnimg.cn/20190817135934958.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="715"></p>
<p><strong>2.1.2 &nbsp;定义 pom.xml</strong></p>
<p>在父工程的 pom.xml 中抽取一些重复的配置的，比如：锁定 jar 包的版本、设置编译版本等。</p>
<p><img alt="" class="has" height="778" src="https://img-blog.csdnimg.cn/20190817140033673.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"></p>
<p><strong>2.1.3&nbsp;将父工程发布至仓库</strong></p>
<p>父工程创建完成执行 install 将父工程发布到仓库方便子工程继承</p>
<p><img alt="" class="has" height="547" src="https://img-blog.csdnimg.cn/20190817140107967.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="671"></p>
<h3 id="2.2%20ssm_dao%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97"><a name="t43"></a>2.2 ssm_dao &nbsp;子模块</h3>
<p><strong>2.2.1 &nbsp;创建 dao 子模块</strong></p>
<p>1、在父工程上右击创建 maven 模块：</p>
<p><img alt="" class="has" height="282" src="https://img-blog.csdnimg.cn/20190817140155447.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="767"></p>
<p>2、选择“跳过骨架选择”：</p>
<p><img alt="" class="has" height="591" src="https://img-blog.csdnimg.cn/20190817140207243.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="769"></p>
<p>3、填写模块名称</p>
<p><img alt="" class="has" height="215" src="https://img-blog.csdnimg.cn/20190817140216551.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="753"></p>
<p>4、下一步，确定项目的目录</p>
<p><img alt="" class="has" height="258" src="https://img-blog.csdnimg.cn/20190817140230803.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="771"></p>
<p>5、打包方式是 jar</p>
<p><img alt="" class="has" height="499" src="https://img-blog.csdnimg.cn/2019081714024474.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="770"></p>
<p><strong>2.2.2 &nbsp;定义 pom.xml</strong></p>
<p>只添加到dao层的 pom，mybatis 和 spring 的整合相关依赖</p>
<p><img alt="" class="has" height="512" src="https://img-blog.csdnimg.cn/20190817140415969.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="778"><img alt="" class="has" height="670" src="https://img-blog.csdnimg.cn/20190817140438555.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="780"><img alt="" class="has" height="619" src="https://img-blog.csdnimg.cn/20190817140457950.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="776"></p>
<p><strong>2.2.3 dao 代码</strong></p>
<p><img alt="" class="has" height="533" src="https://img-blog.csdnimg.cn/20190817140516823.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"></p>
<p><img alt="" class="has" height="409" src="https://img-blog.csdnimg.cn/20190817140523768.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="687"></p>
<p><strong>2.2.4 &nbsp;配置文件</strong></p>
<p>将 applicationContext.xml拆分出一个applicationContext-dao.xml，此文件中只配置 dao 相关</p>
<p><img alt="" class="has" height="664" src="https://img-blog.csdnimg.cn/20190817140556432.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="777"></p>
<p><strong>2.2.5 单元测试</strong></p>
<p><img alt="" class="has" height="626" src="https://img-blog.csdnimg.cn/20190817140624556.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="779"></p>
<p><strong>2.2.6把 dao &nbsp;模块 install &nbsp;到本地仓库</strong></p>
<p><img alt="" class="has" height="402" src="https://img-blog.csdnimg.cn/20190817140649132.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="774"></p>
<h3 id="2.3%20ssm_service%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97."><a name="t44"></a>2.3 ssm_service &nbsp;子模块.</h3>
<p><strong>2.3.1 &nbsp;创建 service &nbsp;子模块</strong></p>
<p>方法同 ssm_dao 模块创建方法，模块名称为 ssm_service。</p>
<p><strong>2.3.2 &nbsp;定义 pom.xml</strong></p>
<p><img alt="" class="has" height="587" src="https://img-blog.csdnimg.cn/20190817140736691.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="796"></p>
<p><strong>2.3.3 service 接口</strong></p>
<p>将 ssm_maven 工程中的service接口拷贝到 src/main/java中：<img alt="" class="has" height="290" src="https://img-blog.csdnimg.cn/20190817140801588.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="581"></p>
<p><strong>2.3.4 配置文件</strong></p>
<p><img alt="" class="has" height="123" src="https://img-blog.csdnimg.cn/20190817140812428.png" width="762"></p>
<p><strong>2.3.5&nbsp;依赖范围对传递依赖的影响（了解）</strong></p>
<p><strong>2.3.5.1 &nbsp;问题描述</strong></p>
<p><img alt="" class="has" height="281" src="https://img-blog.csdnimg.cn/20190817140848572.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="771"></p>
<p><img alt="" class="has" height="71" src="https://img-blog.csdnimg.cn/20190817140856328.png" width="789"></p>
<p><strong>2.3.5.3&nbsp;依赖范围对传递依赖的影响</strong></p>
<p><img alt="" class="has" height="396" src="https://img-blog.csdnimg.cn/20190817140915721.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="795"></p>
<p><img alt="" class="has" height="574" src="https://img-blog.csdnimg.cn/20190817140958237.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="796"></p>
<p><strong>2.3.6 单元测试</strong></p>
<p><img alt="" class="has" height="586" src="https://img-blog.csdnimg.cn/20190817141108995.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="782"></p>
<p><strong>2.3.7 Install 到本地仓库</strong></p>
<p><img alt="" class="has" height="154" src="https://img-blog.csdnimg.cn/20190817141129526.png" width="764"></p>
<h3 id="2.4%20ssm_web%20%C2%A0%E5%AD%90%E6%A8%A1%E5%9D%97"><a name="t45"></a>2.4 ssm_web &nbsp;子模块</h3>
<p><strong>2.4.1 &nbsp;创建 web 子模块</strong></p>
<p><img alt="" class="has" height="336" src="https://img-blog.csdnimg.cn/20190817141154553.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="762"></p>
<p>2、确认使用自己的本地仓库</p>
<p><img alt="" class="has" height="278" src="https://img-blog.csdnimg.cn/20190817141211990.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="772"></p>
<p>3、填写模块名称</p>
<p><img alt="" class="has" height="233" src="https://img-blog.csdnimg.cn/2019081714122443.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="755"></p>
<p>使用骨架创建 web 项目会花费些时间，请耐心等待</p>
<p><img alt="" class="has" height="258" src="https://img-blog.csdnimg.cn/20190817141248790.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="504"></p>
<p>5、添加打包方式war</p>
<p><img alt="" class="has" height="352" src="https://img-blog.csdnimg.cn/20190817141257660.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="679"></p>
<p><strong>2.4.2 &nbsp;定义 pom.xml</strong></p>
<p><img alt="" class="has" height="78" src="https://img-blog.csdnimg.cn/20190817141312316.png" width="799"><img alt="" class="has" height="670" src="https://img-blog.csdnimg.cn/20190817141321173.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="777"></p>
<p><strong>2.4.3 controller</strong></p>
<p><img alt="" class="has" height="307" src="https://img-blog.csdnimg.cn/20190817141337540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="552"></p>
<p><strong>2.4.4&nbsp;配置文件</strong></p>
<p><img alt="" class="has" height="453" src="https://img-blog.csdnimg.cn/20190817141352999.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="613"></p>
<h3 id="2.5%20%C2%A0%E8%BF%90%E8%A1%8C%20%E8%B0%83%E8%AF%95"><a name="t46"></a>2.5 &nbsp;运行 调试</h3>
<blockquote>
<p>方法 1：在ssm_web 工程的 pom.xml 中配置 tomcat 插件运行<br>
运行 ssm_web 工程它会从本地仓库下载依赖的 jar 包，所以当 ssm_web 依赖的 jar 包内容修<br>
改了必须及时发布到本地仓库，比如：ssm_web 依赖的 ssm_service 修改了，需要及时将ssm_service 发布到本地仓库。<br>
方法 2：在父工程的 pom.xml 中配置 tomcat插件运行，自动聚合并执行<br>
推荐方法2，如果子工程都在本地，采用方法2则不需要子工程修改就立即发布到本地仓库，<br>
父工程会自动聚合并使用最新代码执行。</p>
</blockquote>

<p><strong>注意：如果子工程和父工程中都配置了tomcat 插件，运行的端口和路径以子工程为准。</strong></p>
<h2 id="3.%20%C2%A0%E5%88%86%E6%A8%A1%E5%9D%97%E6%9E%84%E5%BB%BA%E5%B7%A5%E7%A8%8B--%20%E4%BE%9D%E8%B5%96%E6%95%B4%E5%90%88"><a name="t47"></a>3. &nbsp;分模块构建工程-- 依赖整合</h2>
<blockquote>
<p>每个模块都需要 spring 或者 junit 的 jar，况且最终 package 打完包最后生成的项目中的jar 就是各个模块依赖的整合，所以我们可以把项目中所需的依赖都可以放到父工程中,模块中只留模块和模块之间的依赖，那父工程的 pom.xml 可以如下配置：</p>
</blockquote>

<p><img alt="" class="has" height="693" src="https://img-blog.csdnimg.cn/20190817141548342.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="690"><img alt="" class="has" height="697" src="https://img-blog.csdnimg.cn/20190817141603941.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="689"><img alt="" class="has" height="433" src="https://img-blog.csdnimg.cn/20190817141613493.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="691"><img alt="" class="has" height="603" src="https://img-blog.csdnimg.cn/20190817141622317.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="693"><img alt="" class="has" height="538" src="https://img-blog.csdnimg.cn/20190817141632873.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="693"><img alt="" class="has" height="717" src="https://img-blog.csdnimg.cn/20190817141643762.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="690"><img alt="" class="has" height="415" src="https://img-blog.csdnimg.cn/20190817141651177.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="694"><img alt="" class="has" height="453" src="https://img-blog.csdnimg.cn/20190817141658567.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="692"><img alt="" class="has" height="370" src="https://img-blog.csdnimg.cn/20190817141704207.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="692"></p>
<h1 id="%E5%9B%9B%E3%80%81%20maven%20%C2%A0%E7%A7%81%E6%9C%8D%5B%20%E4%BA%86%E8%A7%A3%5D"><a name="t48"></a>四、 maven &nbsp;私服[ 了解]</h1>
<h2><a name="t49"></a>1. &nbsp;需求</h2>
<p>正式开发，不同的项目组开发不同的工程。<br>
ssm_dao工程开发完毕，发布到私服。<br>
ssm_service 从私服下载 dao</p>

<h2 id="2.%20%C2%A0%E5%88%86%E6%9E%90"><a name="t50"></a>2. &nbsp;分析</h2>
<p><img alt="" class="has" height="586" src="https://img-blog.csdnimg.cn/20190817141756832.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="694"></p>
<h2 id="3.%C2%A0%E6%90%AD%E5%BB%BA%E7%A7%81%E6%9C%8D%E7%8E%AF%E5%A2%83"><a name="t51"></a>3.&nbsp;搭建私服环境</h2>
<h3 id="3.1%20%C2%A0%E4%B8%8B%E8%BD%BD%20nexus"><a name="t52"></a>3.1 &nbsp;下载 nexus</h3>
<p><img alt="" class="has" height="110" src="https://img-blog.csdnimg.cn/20190817141837286.png" width="703"></p>
<p><img alt="" class="has" height="267" src="https://img-blog.csdnimg.cn/20190817141841851.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="373"></p>
<h3 id="3.2%20%C2%A0%E5%AE%89%E8%A3%85%20nexus"><a name="t53"></a>3.2 &nbsp;安装 nexus</h3>
<p><img alt="" class="has" height="470" src="https://img-blog.csdnimg.cn/2019081714185216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="638"></p>
<h3 id="3.3%20%C2%A0%E5%8D%B8%E8%BD%BD%20nexus"><a name="t54"></a>3.3 &nbsp;卸载 nexus</h3>
<p><img alt="" class="has" height="22" src="https://img-blog.csdnimg.cn/20190817141903268.png" width="411"><img alt="" class="has" height="101" src="https://img-blog.csdnimg.cn/2019081714190976.png" width="688"></p>
<h3 id="3.4%20%C2%A0%E5%90%AF%E5%8A%A8%20nexus"><a name="t55"></a>3.4 &nbsp;启动 nexus</h3>
<p><img alt="" class="has" height="590" src="https://img-blog.csdnimg.cn/20190817141921270.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="576"><img alt="" class="has" height="300" src="https://img-blog.csdnimg.cn/20190817141927921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="590"><img alt="" class="has" height="679" src="https://img-blog.csdnimg.cn/20190817141936263.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="705"><img alt="" class="has" height="371" src="https://img-blog.csdnimg.cn/20190817141940444.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="705"></p>
<h3 id="3.5%20%E4%BB%93%E5%BA%93%E7%B1%BB%E5%9E%8B"><a name="t56"></a>3.5 仓库类型</h3>
<p><img alt="" class="has" height="280" src="https://img-blog.csdnimg.cn/20190817142002286.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="678"></p>
<p><img alt="" class="has" height="666" src="https://img-blog.csdnimg.cn/20190817142010829.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="718"><img alt="" class="has" height="301" src="https://img-blog.csdnimg.cn/20190817142023342.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="393"><img alt="" class="has" height="718" src="https://img-blog.csdnimg.cn/2019081714203019.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="688"></p>
<h2 id="4.%20%C2%A0%E5%B0%86%E9%A1%B9%E7%9B%AE%E5%8F%91%E5%B8%83%E5%88%B0%E7%A7%81%E6%9C%8D"><a name="t57"></a>4. &nbsp;将项目发布到私服</h2>
<h3 id="4.1%20%E9%9C%80%E6%B1%82"><a name="t58"></a>4.1 需求</h3>
<p><img alt="" class="has" height="389" src="https://img-blog.csdnimg.cn/20190817142050414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="714"></p>
<p>4.2 &nbsp;配置</p>
<p><img alt="" class="has" height="455" src="https://img-blog.csdnimg.cn/20190817142105164.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="699"><img alt="" class="has" height="292" src="https://img-blog.csdnimg.cn/20190817142112778.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="712"><img alt="" class="has" height="430" src="https://img-blog.csdnimg.cn/20190817142130497.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="699"></p>
<h3 id="4.3%20%C2%A0%E6%B5%8B%E8%AF%95"><a name="t59"></a>4.3 &nbsp;测试</h3>
<p><img alt="" class="has" height="264" src="https://img-blog.csdnimg.cn/20190817142145830.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="689"><img alt="" class="has" height="612" src="https://img-blog.csdnimg.cn/20190817142153867.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="701"></p>
<h2 id="5.%20%C2%A0%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85"><a name="t60"></a>5. &nbsp;从私服下载 jar 包</h2>
<h3 id="5.1%20%C2%A0%E9%9C%80%E6%B1%82"><a name="t61"></a>5.1 &nbsp;需求</h3>
<p><img alt="" class="has" height="259" src="https://img-blog.csdnimg.cn/20190817142226790.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="707"></p>
<h3 id="5.2%20%C2%A0%E7%AE%A1%E7%90%86%E4%BB%93%E5%BA%93%E7%BB%84"><a name="t62"></a>5.2 &nbsp;管理仓库组</h3>
<p><img alt="" class="has" height="620" src="https://img-blog.csdnimg.cn/20190817142243832.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="701"></p>
<h3 id="5.3%20%E5%9C%A8%20setting.xml%20%C2%A0%E4%B8%AD%E9%85%8D%E7%BD%AE%E4%BB%93%E5%BA%93"><a name="t63"></a>5.3 在 setting.xml &nbsp;中配置仓库</h3>
<p><img alt="" class="has" height="354" src="https://img-blog.csdnimg.cn/20190817142256403.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="697"><img alt="" class="has" height="689" src="https://img-blog.csdnimg.cn/20190817142310125.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="694"><img alt="" class="has" height="411" src="https://img-blog.csdnimg.cn/20190817142327214.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="695"><img alt="" class="has" height="712" src="https://img-blog.csdnimg.cn/20190817142341886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="700"><img alt="" class="has" height="416" src="https://img-blog.csdnimg.cn/20190817142352313.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="694"><img alt="" class="has" height="577" src="https://img-blog.csdnimg.cn/20190817142358721.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="688"></p>
<h3 id="5.4%20%C2%A0%E6%B5%8B%E8%AF%95%E4%BB%8E%E7%A7%81%E6%9C%8D%E4%B8%8B%E8%BD%BD%20jar%20%E5%8C%85"><a name="t64"></a>5.4 &nbsp;测试从私服下载 jar 包</h3>
<p><img alt="" class="has" height="142" src="https://img-blog.csdnimg.cn/201908171424158.png" width="708"><img alt="" class="has" height="505" src="https://img-blog.csdnimg.cn/20190817142432817.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="1103"><img alt="" class="has" height="299" src="https://img-blog.csdnimg.cn/20190817142447200.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="708"></p>
<h1 id="%E4%BA%94%E3%80%81%20%C2%A0%E6%8A%8A%E7%AC%AC%E4%B8%89%E6%96%B9%20jar%20%C2%A0%E5%8C%85%E6%94%BE%E5%85%A5%E6%9C%AC%E5%9C%B0%E4%BB%93%E5%BA%93%E6%88%96%E7%A7%81%E6%9C%8D"><a name="t65"></a>五、 &nbsp;把第三方 jar &nbsp;包放入本地仓库或私服</h1>
<h2 id="1.%20%C2%A0%E5%AF%BC%E5%85%A5%E6%9C%AC%E5%9C%B0%E5%BA%93"><a name="t66"></a>1. &nbsp;导入本地库</h2>
<p><img alt="" class="has" height="131" src="https://img-blog.csdnimg.cn/20190817142510611.png" width="702"><img alt="" class="has" height="360" src="https://img-blog.csdnimg.cn/20190817142519931.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="1063"><img alt="" class="has" height="144" src="https://img-blog.csdnimg.cn/20190817142526195.png" width="754"></p>
<h2 id="2.%20%E5%AF%BC%E5%85%A5%E7%A7%81%E6%9C%8D"><a name="t67"></a>2. 导入私服</h2>
<p><img alt="" class="has" height="505" src="https://img-blog.csdnimg.cn/20190817142546969.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="711"><img alt="" class="has" height="594" src="https://img-blog.csdnimg.cn/20190817142612486.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="1116"><img alt="" class="has" height="263" src="https://img-blog.csdnimg.cn/2019081714262048.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="671"></p>
<h2 id="3.%20%E5%8F%82%E6%95%B0%E8%AF%B4%E6%98%8E"><a name="t68"></a>3. 参数说明</h2>
<p><img alt="" class="has" height="297" src="https://img-blog.csdnimg.cn/20190817142634378.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2OTEwNjM0,size_16,color_FFFFFF,t_70" width="694"><img alt="" class="has" height="106" src="https://img-blog.csdnimg.cn/20190817142642333.png" width="684"></p>
<p>&nbsp;</p>