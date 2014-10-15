title: 图片上传跨域解决方法
date: 2014-10-14 15:43:33
tags: [javascript]
description: 利用iframe以及jquery进行表单post提交
photos:
- http://bruce.u.qiniudn.com/2013/11/27/reading/photos-0.jpg
- http://bruce.u.qiniudn.com/2013/11/27/reading/photos-1.jpg
---
  ## 利用iframe以及jquery进行表单post提交

```
<script type="text/javascript" src="http://code.jquery.com/jquery-1.7.2.js"></script>
<script type="text/javascript" src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
<script type="text/javascript">
  $(document).ready(function() {  
     $("#file").bind("change", function() {//对文件输入框绑定change事件
             $("#form").submit();  
     });  
})
</script>

<body>
     <form action="跨域名接口" id="form" name="form"   
          enctype="multipart/form-data" method="post" target="hidden_frame">  
        <span>  
     
            <input type="file" id="file" name="file"/>  
        </span>  
        <iframe name="hidden_frame" id="hidden_frame" style="display:none"></iframe>  
    </form>
</body>
```
　　form的target要指定iframe的名称，这样就看不到页面的跳转了 。

    target的几个属性值 ：

	值                描述
	_blank       在新窗口中打开。
	_self        默认。在相同的框架中打开。
	_parent      在父框架集中打开。
	_top         在整个窗口中打开。
	framename    在指定的框架中打开。
	我们可以看到form表单提交后页面没有做跳转，并且返回值，也在隐藏的iframe中展现。正体现了target的这种妙用。
