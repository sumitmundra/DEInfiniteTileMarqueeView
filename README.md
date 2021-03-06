
# DEInfiniteTileMarqueeView

[https://github.com/dreamengine/DEInfiniteTileMarqueeView](https://github.com/dreamengine/DEInfiniteTileMarqueeView)

## What It Does

`DEInfiniteTileMarqueeView` is a self-contained widget that takes an image, tiles it horizontally, and makes the tiles scroll forever. Great for futuristic UI effects (or a marquee screensaver). Both IB and programmatic friendly.

![Example gif](DEInfiniteTileMarqueeView.gif?raw=true)

(The framerate is slow in the gif: the actual widget will render smoothly.)

## How It Works

First, make sure that your marquee view's width is an integer multiple of the tileImage width, otherwise there will be visual looping issues. Also, the marquee view's height should match the image's height.

Then, specify a direction (left-to-right or right-to-left), an image to tile, and how long it takes for a tile to scroll across its width, and you're done.

### Example

	-(void)viewDidLoad {
		// width is 5x image width, height is the same as image height
		self.marqueeView = [[DEInfiniteTileMarqueeView alloc] initWithFrame:CGRectMake(0.f,0.f,100.f,20.f)];	
		
		self.marqueeView.direction = DEInfiniteTileMarqueeViewDirectionRightToLeft;
		
		// this will load an image where width = height = 20pt
		UIImage *marqueeImage = [UIImage imageNamed:@"..."];
		
	    self.marqueeView.tileImage = marqueeImage;
	    
	    self.marqueeView.tileDuration = 0.5;
	}