<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>js倒计时代码</title>
<style type="text/css">
* {
        margin: 0;
        padding: 0;
}
body{ text-align:center;}
ul, li {
        list-style: none;
}
#show_time {
        color: #f00;
        font-size: 24px;
        font-weight: bold;
        width:100%;
        text-align:center;
        padding-top:30px;
}
</style>
</head>
<body>
<div id="show_time"> </div>
<script type="text/javascript"> 
function countdown(){
    var show_time = document.getElementById("show_time");
    endtime = new Date("9/3/2015 23:59:59");//结束时间
    today = new Date();//当前时间
    delta_T = endtime.getTime() - today.getTime();//时间间隔
    if(delta_T < 0){
        clearInterval(auto);
        show_time.innerHTML = "倒计时已经结束";
    }
    window.setTimeout(countdown,1000);
    total_days = delta_T/(24*60*60*1000);//总天数
    total_show = Math.floor(total_days);//实际显示的天数
    total_hours = (total_days - total_show)*24;//剩余小时
    hours_show = Math.floor(total_hours);//实际显示的小时数
    total_minutes = (total_hours - hours_show)*60;//剩余的分钟数
    minutes_show = Math.floor(total_minutes);//实际显示的分钟数
    total_seconds = (total_minutes - minutes_show)*60;//剩余的分钟数
    seconds_show = Math.floor(total_seconds);//实际显示的秒数
    show_time.innerHTML = "距离2015年9月3日还有:" + total_show + "天" + hours_show + "时" + minutes_show + "分" + seconds_show + "秒";
}
countdown();
</script>
</body>
</html>

