#Introduce
We forked the project from https://github.com/OpenFlutter/k_chart
and add some function to meet our requirments.

all the version below are the version we released.


## [0.5.1]
* added the function that will show buy sell signal on the charts

## [0.5.2]
* support set scale-x from parameter when build widget.it solve the problem that on the flutter web,the gesture scale not work.

## [0.5.3]
* support extra line draw on the charts



how to publish:
https://dart.cn/tools/pub/publishing


------
# Raw README.md from forked project
# k_chart
Maybe this is the best k chart in Flutter.Support drag,scale,long press,fling.And easy to use.

## display

#### image

<img src="https://github.com/mafanwei/k_chart/blob/master/example/images/Screenshot1.jpg" width="375" alt="Screenshot"/>

<img src="https://github.com/mafanwei/k_chart/blob/master/example/images/Screenshot2.jpg" width="375" alt="Screenshot"/>

<img src="https://github.com/mafanwei/k_chart/blob/master/example/images/Screenshot3.jpeg" width="375" alt="Screenshot"/>

#### gif

![demo](https://github.com/mafanwei/k_chart/blob/master/example/images/demo.gif)

![demo](https://github.com/mafanwei/k_chart/blob/master/example/images/demo2.gif)

## Getting Started
#### Install
```
dependencies:
  k_chart: ^0.5.0
```
or use latest：
```
k_chart:
    git:
      url: https://github.com/mafanwei/k_chart
```
#### Usage

**When you change the data, you must call this:**
```dart
DataUtil.calculate(datas); //This function has some optional parameters: n is BOLL N-day closing price. k is BOLL param.
```

use k line chart:
```dart
Container(
              height: 450,
              width: double.infinity,
              child: KChartWidget(
                chartStyle, // Required for styling purposes
                chartColors,// Required for styling purposes
                datas,// Required，Data must be an ordered list，(history=>now)
                isLine: isLine,// Decide whether it is k-line or time-sharing
                mainState: _mainState,// Decide what the main view shows
                secondaryState: _secondaryState,// Decide what the sub view shows
                fixedLength: 2,// Displayed decimal precision
                timeFormat: TimeFormat.YEAR_MONTH_DAY,
                onLoadMore: (bool a) {},// Called when the data scrolls to the end. When a is true, it means the user is pulled to the end of the right side of the data. When a
                // is false, it means the user is pulled to the end of the left side of the data.
                maDayList: [5,10,20],// Display of MA,This parameter must be equal to DataUtil.calculate‘s maDayList
                bgColor: [Colors.black, Colors.black],// The background color of the chart is gradient
                translations: kChartTranslations,// Graphic language
                volHidden: false,// hide volume
                showNowPrice: true,// show now price
                isOnDrag: (isDrag){},// true is on Drag.Don't load data while Draging.
                onSecondaryTap:(){}// on secondary rect taped.
              ),
            ),
```
use TrendLine(New): You can use Trendline by long-pressing and moving your finger after setting true to isTrendLine property.  
use depth chart:
```dart
DepthChart(_bids, _asks, chartColors) //Note: Datas must be an ordered list，
```

#### Donate

Buy a cup of coffee for the author.

<img src="https://img-blog.csdnimg.cn/20181205161540134.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3F3ZTI1ODc4,size_16,color_FFFFFF,t_70" width="375" alt="alipay"/>
<img src="https://img-blog.csdnimg.cn/20181205162201519.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3F3ZTI1ODc4,size_16,color_FFFFFF,t_70" width="375" alt="wechat"/>

#### Thanks
[gwhcn/flutter_k_chart](https://github.com/gwhcn/flutter_k_chart)

#### Other
Maybe there are some bugs in this k chart,or you want new indicators,you can create a pull request.I will happy to accept it and I hope we can make it better.

----------

The version of fork