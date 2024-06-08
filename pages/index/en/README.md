---
title: Easy form Android to Windows
keywords: Easy-aToWin, Android, Windows, Flashable ZIP, Windows Flashable ZIP, Android ROMs,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, Android to Windows, Xiaomi Flash Windows, Oneplus Flash Windows, Radmi flash Windows, Yemon
desc: Easy-aToWin, Easy Android to Windows, Flashable ZIPs to convert SDM 845/855 devices from Android to Windows
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
            <h3>Flashable ZIPs to convert SDM 845/855 devices from Android to Windows</h3>
            test text
        </div>
        <div class="big_btn_wrapper">
            <div class="big_btn">
                <a href="#" id="learn_more">Learn More</a>
            </div>
            <div class="big_btn">
                <a href="/user/zh/">Get Started</a>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_left">
        <div>
            <div class="dsc_left">
                <h2>Say goodbye to hassle</h2>
                <h2>No need PC</h2>
                <h2>Simple and swift</h2>
            </div>
            <div class="dsc_right">
                <h3>Just two steps</h3>
                Partition --> flashed
                <h3>Enjoy</h3>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_right">
        <div>
            <div class="dsc_left">
                Thoroughly tested prior to launch, ensuring stability and universality.</br>
                The update-binary is compatible with the vast majority of devices, with custom solutions available for unique models.
            </div>
            <div class="dsc_right">
                <h2>Stable and universal</h2>
                <h2>Easily adaptable</h2>
            </div>
        </div>
    </div>
    <div class="section dsc_wrapper_left">
        <div>
            <div class="dsc_left">
                <h2>stop scrolling down</h2>
                <h2>The homepage is not fully completed</h2>
            </div>
            <div class="dsc_right">
                I don't understand English<br>
                So I need a translator
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

