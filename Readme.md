Snoopy使用方法
----
它是用来模拟浏览器的功能，可以获取网页内容，网页链接，发送表单，可以用来快速开发一些采集程序和小偷程序。

#####案例一：获取网页内容，纯文本内容，网页链接，网页表单

    <?php
    include("snoopy.class.php");
    $url = "http://pr.phpddt.com";   
    $snoopy = new Snoopy;
    //获取网页所有内容
    $snoopy->fetch($url);
    //获取网页纯文本内容
    $snoopy->fetchtext($url);
    //获取网页所有链接
    $snoopy->fetchlinks ($url);
    //获取网页表单
    $snoopy->fetchform($url);
 
    //打印查看
    print_r($snoopy->results);

#####案例二：模拟登录，简单的令人咋舌啊。。。

    <?php
    /**
    * 这里模拟登录我的博客
    *
    * @link http://www.phpddt.com
    */
    include("snoopy.class.php");
    $snoopy = new Snoopy;
  
    $submit_url = "http://blog.phpddt.com/admin/login";
    $submit_vars['name'] = "密码";
    $submit_vars['password'] = "你不不会知道的";
    $snoopy->submit($submit_url, $submit_vars);
    //登录后的结果
    print $snoopy->results;