## PCH头文件

#### pch文件设置:

Build Settings / Apple LLVM 7.0 - Language / Prefix Header

```
$(SRCROOT)/项目名称/头文件名称.pch
```

#### pch文件的作用:

* 存放一些全局的宏(整个项目中都用得上的宏)
* 用来包含一些全部的头文件(整个项目中都用得上的头文件)
* 能自动打开或者关闭日志输出功能

```

	#ifdef __OBJC__
    	#import <UIKit/UIKit.h>
    	#import <Foundation/Foundation.h>

	/** 打印输出 */
	#ifdef DEBUG  // 调试阶段
	#define KLog(...) NSLog(__VA_ARGS__)
	#else // 发布阶段
	#define KLog(...)
	#endif
	
	// 屏幕宽高
	#define SCREEN_WIDTH ([UIScreen mainScreen].bounds.size.width)
	#define SCREEN_HEIGHT ([UIScreen mainScreen].bounds.size.height)
	
	// RGB颜色
	#define kCOLOR(R ,G ,B ,A) [UIColor colorWithRed:(R) / 255.0 green:(G) / 255.0 blue:(B) / 255.0 alpha:A]
	
	// 随机色
	#define kRandomColor kCOLOR(arc4random() % 256, arc4random() % 256, arc4random() % 256, 1)

	//各种view按手机屏幕大小缩放时，用到的基准宽和高
	#define kScaleWidth(width)  (SCREEN_WIDTH / 375 * width)
	#define kScaleHeight(height)  (SCREEN_HEIGHT / 667 * height)
	
	
	#endif
	
```