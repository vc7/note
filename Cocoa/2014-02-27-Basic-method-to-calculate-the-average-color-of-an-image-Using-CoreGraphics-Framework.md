# Basic method to calculate the average color of an image - Using CoreGraphics Framework

------

Related solutions and articles

* [http://stackoverflow.com/a/13695592/1583560](http://stackoverflow.com/a/13695592/1583560)
* [http://www.bobbygeorgescu.com/2011/08/finding-average-color-of-uiimage/](http://www.bobbygeorgescu.com/2011/08/finding-average-color-of-uiimage/)

------
```
-(UIColor*)averageColor {
	CGColorSpaceRef colorSpace =CGColorSpaceCreateDeviceRGB();
	unsignedchar rgba[4];
	CGContextRef context =CGBitmapContextCreate(rgba,1,1,8,4, colorSpace, kCGImageAlphaPremultipliedLast | kCGBitmapByteOrder32Big);
	
	CGContextDrawImage(context,CGRectMake(0,0,1,1), self.CGImage);
	CGColorSpaceRelease(colorSpace);
	CGContextRelease(context);
	
	if(rgba[3]]]>0)
	{
		CGFloat alpha =((CGFloat)rgba[3])/255.0;
		CGFloat multiplier = alpha/255.0;
		return [UIColor colorWithRed:((CGFloat)rgba[0])*multiplier
		                       green:((CGFloat)rgba[1])*multiplier
		                        blue:((CGFloat)rgba[2])*multiplier
		                       alpha:alpha];
                               
	}
	else
	{
    	return [UIColor colorWithRed:((CGFloat)rgba[0])/255.0
		                       green:((CGFloat)rgba[1])/255.0                                
		                        blue:((CGFloat)rgba[2])/255.0                               
		                       alpha:((CGFloat)rgba[3])/255.0];
	}
}
```