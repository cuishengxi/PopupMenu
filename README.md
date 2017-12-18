# PopupMenu
QQ菜单、微信 右上角+号==按钮弹出的可变菜单，
在别人的基础上做了完善，称之为`DavidPopupMenu`。简称`DP`，有兴趣的可以用一下。
****

|Author|崔盛希|
|---|---
|E-mail|1300000608@qq.com

***效果图：***
----------------------
![](https://github.com/cuishengxi/PopupMenu/blob/master/屏幕快照%202017-12-18%20下午4.45.38.png?raw=true)

-----------------------
###使用方法
```Objective-c

- (IBAction)sender:(UIButton *)sender {
if (!sender.selected) {

NSArray*menuArr=@[
[PopupMenuItem menuItem:@"我" image:[UIImage imageNamed:@"hyq"] target:self action:@selector(menuClick:)],
[PopupMenuItem menuItem:@"爱" image:[UIImage imageNamed:@"hyq"] target:self action:@selector(menuClick:)],
[PopupMenuItem menuItem:@"你" image:[UIImage imageNamed:@"hyq"] target:self action:@selector(menuClick:)],
[PopupMenuItem menuItem:@"中" image:[UIImage imageNamed:@"hyq"] target:self action:@selector(menuClick:)],
[PopupMenuItem menuItem:@"国" image:[UIImage imageNamed:@"hyq"] target:self action:@selector(menuClick:)]];
[Popup setTitleFont:[UIFont systemFontOfSize:15]];
OptionalConfiguration options=DavidOptionalConfigurationMake(9, 7, 9, 25, true, false, 
true, true, false, DavidColorMake(0, 0, 0), DavidColorMake(1, 1, 1));
[Popup showMenuInView:self.view fromRect:sender.frame menuItems:menuArr withOptions:options]; //显示下拉菜单
}else{
[Popup dismissMenu]; //下拉菜单消失

}

}

-(void)menuClick:(PopupMenuItem*)sender{
NSLog(@"===%@",sender.title);
}


```

***注意***
使用的图片不能太大了（小于单行的高度），大了会超出！一般都是使用的小图标。有兴趣的，可以再优化了！



