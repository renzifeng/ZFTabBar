# ZFTabBar
**自定义TabBar，可以选中和非选中图片，还可以加badgeValue**

### 效果演示：
![image](https://github.com/renzifeng/ZFTabBar.git/ScreenShot.png)

#用法示例

## 初始化TabBar
``` objc
/**
*  初始化所有的子控制器
*/
- (void)setupAllChildViewControllers
{
    // 1.首页
    FirstViewController *home = [[FirstViewController alloc] init];
    home.tabBarItem.badgeValue = @"N";
    [self setupChildViewController:home title:@"首页" imageName:@"shouye" selectedImageName:@"shouye_s"];

    // 2.消息
    SecondViewController *message = [[SecondViewController alloc] init];
    message.tabBarItem.badgeValue = @"8";
    [self setupChildViewController:message title:@"消息" imageName:@"quanzi" selectedImageName:@"quanzi_s"];

    // 3.首页
    FirstViewController *home1 = [[FirstViewController alloc] init];
    home1.tabBarItem.badgeValue = @"19";
    [self setupChildViewController:home1 title:@"发现" imageName:@"shouye" selectedImageName:@"shouye_s"];

    // 4.消息
    SecondViewController *message1 = [[SecondViewController alloc] init];
    message1.tabBarItem.badgeValue = @"99";
    [self setupChildViewController:message1 title:@"广场" imageName:@"quanzi" selectedImageName:@"quanzi_s"];
}
```
## 双击tabbar，可刷新当前页面列表，具体看代码
```objc
/**
*  监听tabbar按钮的改变
*  @param from   原来选中的位置
*  @param to     最新选中的位置
*/
- (void)tabBar:(ZFTabBar *)tabBar didSelectedButtonFrom:(NSInteger)from to:(NSInteger)to
{
    if (self.selectedIndex == to && to == 0 ) {//双击刷新制定页面的列表
        UINavigationController *nav = self.viewControllers[0];
        FirstViewController *firstVC = nav.viewControllers[0];
        [firstVC refrshUI];
    }
    self.selectedIndex = to;
}

```
# 期待
- 如果在使用过程中遇到BUG，或发现功能不够用，希望你能Issues我
- 如果觉得好用请Star!
- 谢谢!