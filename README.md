# preview_upload_php
可预览图片上传
是这样的，我前段时间做了一个微信端项目，要实现图片上传，前端部分其实网上一查就找到了，用H5的新api，具体就是datatransfer来做的，但是因为这样一弄，是实现了图片预览的功能，但是现在数据变成了data格式的了，不再是传统的png,jpeg格式的了，我当时也不知道怎么处理，后来我发现可以用php::input协议来做，刚在网上又找了下，发现了这个东西，测试了下可以用
## todo 具体需要修改些地方的bug
- 比如图片的格式要判断，不能写死,或者好像$_FILES可以读取格式，拼接的时候用
- 这个类好像是针对根目录写的，还需要用常量来拼一个正确的地址

不过，基本上是可以解决预览加上传问题了

附带一个如何服务器给本地传base64方法
$img_file = file_get_contents("http://www.oschina.net/img/logo_s2.png");
echo base64_encode($img_file);

<input type="button" id="btn" value="免费获取验证码" />  
<script type="text/javascript">  
var wait=60;  
function time(o) {  
        if (wait == 0) {  
            o.removeAttribute("disabled");            
            o.value="免费获取验证码";  
            wait = 60;  
        } else {  
            o.setAttribute("disabled", true);  
            o.value="重新发送(" + wait + ")";  
            wait--;  
            setTimeout(function() {  
                time(o)  
            },  
            1000)  
        }  
    }  
document.getElementById("btn").onclick=function(){time(this);}  
</script>  
