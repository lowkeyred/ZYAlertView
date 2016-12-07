# ZYAlertView
<pre><code>
//按钮点击事件
-(void) _buttonOptionPressed:(UIButton *)optionButton{<br />
	//convertRect: toView 获取到屏幕上该控件的绝对位置。<br />
	UIWindow * window = [[UIApplication sharedApplication].delegate window]; <br />
	CGRect frame = [optionButton convertRect:optionButton.bounds toView:window];<br />
	ZYAlertMessageView *alertView = [[ZYAlertMessageView alloc] initWithFrame:CGRectMake(self.view.bounds.origin.x,self.view.bounds.origin.y, self.view.bounds.size.width,self.view.bounds.size.height+64)];//self.view.bounds<br />
	//标题数组<br />
	alertView.option_optionContents = @[@"发起活动",@"我参与的"];<br />
	//图片数组<br />
	//alertView.option_optionImages = @[@"image1",@"image2"];<br />
	//使用链式语法直接展示 无需再写 [alertView option_show];<br />
	[[alertView option_setupPopOption:^(NSInteger index, NSString *content) {<br />
	//点击回调<br />
	NSLog(@"你选中了第%ld行 %@", index, content);<br />
	SearchFriendViewController *search = [[SearchFriendViewController 	alloc]init];<br />
	[self.navigationController pushViewController:search animated:YES];<br />
	} whichFrame:frame animate:YES] option_show];<br />
	}<br />
</code></pre>

![image](D4FA56CF34CF8C71280A2F8083FED417.png)
