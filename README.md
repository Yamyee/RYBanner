# RYBanner

     初始化并设置属性
    _banner = [[RYBanner alloc]initWithFrame:CGRectMake(0, 64, self.view.bounds.size.width, 260)];
    _banner.delegate = self;
    _banner.timeInterval = 3;
    _banner.pageCtrlEnable = YES;
    _banner.scrollDirection = RYBannerScrollDirectionRight;
    _banner.pageCtrlPosition = PageCtrlPositionCenter;
    _banner.transitionAnimation = RYBannerTransitionAnimationWeb;
    _banner.placeHolder = [UIImage imageNamed:@"hy_sy_banner"];
    [self.view addSubview:_banner];
    
    刷新数据
    [_banner reloadImages:data];
     
    属性
    //设置滚动时间间隔
    @property (nonatomic,assign)NSInteger timeInterval;
    //设置代理 如果显示有问题请设置delegate
    @property (nonatomic,assign)id<RYBannerDelegate> delegate;
    //滚动方向
    @property (nonatomic,assign)RYBannerScrollDirection scrollDirection;

    //设置页面控制器位置
    @property (nonatomic,assign)PageCtrlPosition pageCtrlPosition;
    //设置页面控制器能否显示
    @property (nonatomic,assign)BOOL pageCtrlEnable;
    //设置当前页面圆点颜色
    @property (nonatomic,strong)UIColor * currentPageIndicatorTintColor;
    //设置其他圆点颜色
    @property (nonatomic,strong)UIColor * pageIndicatorTintColor;
    //占位图片
    @property (nonatomic,strong)UIImage * placeHolder;
    //刷新数据
    -(void)reloadImages:(NSArray *)data;
    //重启定时器
    -(void)startTimer;
    //暂停定时器
    -(void)pauseTimer;
