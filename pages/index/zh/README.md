
---
title: 轻松从安卓跨越到Windows
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
id: home_page
---

<div>
    <!-- <script src="/static/js/scrolloverflow.min.js"></script> -->
    <script src="/static/js/jquery.fullpage.min.js"></script>
    <link rel="stylesheet" href="/static/css/jquery.fullpage.min.css" type="text/css"/>
</div>

<div id="fullpage">
    <div class="section" style="height: 100vh;">
        <div>
            <h1><span>Easy-aToWin</span></h1>
            <h3>骁龙845/855等机型从安卓到windows的刷机包</h3>
            测试文本
        </div>
        <div class="big_btn_wrapper">
            <div class="big_btn">
                <a href="#" id="learn_more">查看更多</a>
            </div>
            <div class="big_btn">
                <a href="/user/zh/">开始使用</a>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_left">
        <div>
            <div class="dsc_left">
                <h2>拒绝麻烦</h2>
                <h2>无需电脑</h2>
                <h2>简单快速</h2>
            </div>
            <div class="dsc_right">
                <h3>只需两步</h3>
                分区 --> 刷入
                <h3>享受</h3>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_right">
        <div>
            <div class="dsc_left">
                上线之前经过详细测试，确保稳定通用</br>
                脚本适应于绝大部分机型，特殊机型可单独定制
            </div>
            <div class="dsc_right">
                <h2>稳定通用</h2>
                <h2>方便适配</h2>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_left">
        <div>
            <div class="dsc_left">
                <h2>别划了</h2>
                <h2>首页没写完</h2>
            </div>
            <div class="dsc_right">
                本来主页就是随便写的
                <br>
                写的我头疼死了，快来个人帮我写
            </div>
        </div>
    </div>
</div>

<div>
<script type='text/javascript'>
    $(document).ready(function () {
        var html = $("#page_footer").html();
        $("#page_footer").remove();
        $("#fullpage").append('<div id="page_footer" class="section fp-auto-height">' + html + "</div>");
        var nav_height = $("#navbar").height();
        $('#fullpage').fullpage({
            menu: '#navbar',
            navigation: true,
            css3: true,
            // dragAndMove: true,
            paddingBottom: nav_height + "px"
            // scrollOverflow: true,
	        // scrollOverflowReset: true,
            // fixedElements: "#navbar"
        });
        $("#learn_more").on("click", function(){
            $.fn.fullpage.moveTo(2);
        });
        $("#to_top").on("click", function(){
            $.fn.fullpage.moveTo(1);
        });
    });
</script>
</div>

<canvas id="backgroundCanvas"  style="top:0; bottom:0; left:0; right:0; position:fixed; z-index: -99;">
</canvas>
<script>
    var isDark = false;
    function createCanvas(dark = null){
        var c=document.getElementById("backgroundCanvas");
        c.height = document.body.clientHeight;
        c.width = document.body.clientWidth;
        var ctx=c.getContext("2d");
        if(dark == null){
            if(getTheme() == "dark"){
                dark = true;
            }else{
                dark = false;
            }
        }
        if(dark){
            ctx.fillStyle="#171717";
            isDark = true;
        }else{
            ctx.fillStyle="#f6f6f6";
            isDark = false;
        }
        var rect = [
    [0.05, 0.3, 0.05, 0.03],
    [0.1, 0.6, 0.05, 0.03],
    [0.12, 0.4, 0.05, 0.13],
    [0.22, 0.35, 0.13, 0.12],
    [0.05, 0.8, 0.1, 0.1],
    [0.18, 0.7, 0.16, 0.14],
    [0.95, 0.2, 0.05, 0.03],
    [0.9, 0.6, 0.05, 0.03],
    [0.7, 0.5, 0.05, 0.13],
    [0.78, 0.35, 0.13, 0.12],
    [0.8, 0.8, 0.16, 0.14],
    [0.6, 0.7, 0.1, 0.24],
    ];
        rect.forEach(function(v, index, array) {
            ctx.fillRect(v[0] * c.width, v[1] * c.height, v[2] * c.width, v[3] * c.height);
        });
    }
    $(window).resize(function() {
        createCanvas();
    });
    $("#themes").on("click", function(){
        createCanvas(!isDark);
    });
    $().ready(function(){
            createCanvas();
        });
</script>
