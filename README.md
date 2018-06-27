# Dialog
Dialog.js 移动端弹窗

![image](https://github.com/Takeos/Dialog/blob/master/demo.gif)

```
Dialog.init('测试文字') //默认
Dialog.init('测试文字',2000) //第二个参数时间，2秒后自动关闭
Dialog.init('测试文字',{
    time : 1000,  //自动关闭
    maskClick : false, //点击背景层是否关闭弹层
    mask : false, //是否显示遮罩
    title : '是否删除？', //添加标题
    index : 1,  //设置索引，用于close方法
    addClass : 'bgRed', //追加class
    style : 'color:red', //追加css
    button : { //按钮
        确定 : function(){
            Dialog.init('你点击了确定',1000);
            Dialog.close(this);
        },
        取消 : function(){
            Dialog.init('你点击了取消',1000)
            Dialog.close(this);
        }
    },
    before : function(){
        //this.classList.add('autoWidth')
        //dom创建成功，但未渲染
        console.log('创建成功',this);
    },
    after : function(){
        console.log('关闭成功',this)
    },
    onload : function(){
        console.log('加载成功',this)
    }
});
//关闭
Dialog.close(this); //在内部使用可直接使用this
Dialog.close(this,function(){ ... }); //可以添加回调
Dialog.close(1,function(){
    //手动关闭弹层，第一个参数为索引值（配合上面index参数使用）；
    //第二个参数为回调
});
```
