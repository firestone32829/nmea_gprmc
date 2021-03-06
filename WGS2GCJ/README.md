<<<<<<< HEAD
C/C++ 使用ChinaMapShift库 测试互转: 地球WGS-84 火星GCJ-02 百度BD-09


**重点内容**必应-中国地图 采用的是火星坐标
http://cn.bing.com/ditu/
	
	**重点内容**NMEA Tools 采集的度分格式要先转成小数格式
	**重点内容**再转成火星坐标，才能在中国地图上对应。
算法库只能自己下载了	
https://github.com/Dronaldo17/ChinaMapShift
	Algorithm for the map offset problem in China. 
	**重点内容**解决中国地图偏移问题的算法。
	
![必应-中国地图 采用的是火星坐标](https://github.com/hongwenjun/nmea_gprmc/blob/master/WGS2GCJ/WGS2GCJ.png) 

***
测试代码
```
#include <iostream>
#include <string>
#include <stdio.h>
#include "china_shift.h"
#include <iomanip>

// Transform WGS-84 to GCJ-02 (Chinese encrypted coordination system)

//    typedef struct {
//        double lng;
//        double lat;
//    } Location;
//
//    Location transformFromWGSToGCJ(Location wgLoc);
//    Location transformFromGCJToWGS(Location gcLoc);
//    Location bd_encrypt(Location gcLoc);
//    Location bd_decrypt(Location bdLoc);


using namespace std;

int main()
{

    puts("地球WGS-84 转 火星GCJ-02 转  百度BD-09");

    Location gps = { 119.465265, 29.1934702};
    cout << setprecision(9) << "地球WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromWGSToGCJ(gps);
    cout << "火星GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_encrypt(gps);
    cout << "百度 BD-09: "  << gps.lat << "  " << gps.lng << endl;

    cout << endl << endl;



    puts("百度BD-09  转 火星GCJ-02 转  地球WGS-84");

    gps = { 119.476936, 29.196518};
    cout << "百度 BD-09: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_decrypt(gps);
    cout << "火星GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromGCJToWGS(gps);
    cout << "地球WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    return 0;
}


```
***
```
地球WGS-84 转 火星GCJ-02 转  百度BD-09
地球WGS-84: 29.1934702  119.465265
火星GCJ-02: 29.1908196  119.470341
百度 BD-09: 29.1965172  119.476936


百度BD-09  转 火星GCJ-02 转  地球WGS-84
百度 BD-09: 29.196518  119.476936
火星GCJ-02: 29.1908195  119.470342
地球WGS-84: 29.1934702  119.465265

以上是输出结果，使用百度API地图取的点，能转到WGS-84坐标，在 maps.google.com上地图对应。 
Google地图中国版，方便把输入几个火星坐标，通过如下方式连接起来，%09是转义符
http://www.google.cn/maps/dir/29.1934702%09119.465265/29.1908196%09119.470341/29.1965172%09119.476936/

```
相关链接
https://github.com/hongwenjun/nmea_gprmc
https://github.com/hongwenjun/TrajectoryCombine

 
=======
#C/C++ 浣跨敤ChinaMapShift搴� 娴嬭瘯浜掕浆: 鍦扮悆WGS-84 鐏槦GCJ-02 鐧惧害BD-09


**閲嶇偣鍐呭**蹇呭簲-涓浗鍦板浘 閲囩敤鐨勬槸鐏槦鍧愭爣
	http://cn.bing.com/ditu/
	
**閲嶇偣鍐呭**NMEA Tools 閲囬泦鐨勫害鍒嗘牸寮忚鍏堣浆鎴愬皬鏁版牸寮�
**閲嶇偣鍐呭**鍐嶈浆鎴愮伀鏄熷潗鏍囷紝鎵嶈兘鍦ㄤ腑鍥藉湴鍥句笂瀵瑰簲銆�
	绠楁硶搴撳彧鑳借嚜宸变笅杞戒簡	
	https://github.com/Dronaldo17/ChinaMapShift

	Algorithm for the map offset problem in China. 
**閲嶇偣鍐呭**瑙ｅ喅涓浗鍦板浘鍋忕Щ闂鐨勭畻娉曘��
	
![蹇呭簲-涓浗鍦板浘 閲囩敤鐨勬槸鐏槦鍧愭爣](https://github.com/hongwenjun/nmea_gprmc/blob/master/WGS2GCJ/WGS2GCJ.png) 

***
娴嬭瘯浠ｇ爜
```
#include <iostream>
#include <string>
#include <stdio.h>
#include "china_shift.h"
#include <iomanip>

// Transform WGS-84 to GCJ-02 (Chinese encrypted coordination system)

//    typedef struct {
//        double lng;
//        double lat;
//    } Location;
//
//    Location transformFromWGSToGCJ(Location wgLoc);
//    Location transformFromGCJToWGS(Location gcLoc);
//    Location bd_encrypt(Location gcLoc);
//    Location bd_decrypt(Location bdLoc);


using namespace std;

int main()
{

    puts("鍦扮悆WGS-84 杞� 鐏槦GCJ-02 杞�  鐧惧害BD-09");

    Location gps = { 119.465265, 29.1934702};
    cout << setprecision(9) << "鍦扮悆WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromWGSToGCJ(gps);
    cout << "鐏槦GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_encrypt(gps);
    cout << "鐧惧害 BD-09: "  << gps.lat << "  " << gps.lng << endl;

    cout << endl << endl;



    puts("鐧惧害BD-09  杞� 鐏槦GCJ-02 杞�  鍦扮悆WGS-84");

    gps = { 119.476936, 29.196518};
    cout << "鐧惧害 BD-09: "  << gps.lat << "  " << gps.lng << endl;

    gps = bd_decrypt(gps);
    cout << "鐏槦GCJ-02: "  << gps.lat << "  " << gps.lng << endl;

    gps = transformFromGCJToWGS(gps);
    cout << "鍦扮悆WGS-84: "  << gps.lat << "  " << gps.lng << endl;

    return 0;
}


```
***
```
鍦扮悆WGS-84 杞� 鐏槦GCJ-02 杞�  鐧惧害BD-09
鍦扮悆WGS-84: 29.1934702  119.465265
鐏槦GCJ-02: 29.1908196  119.470341
鐧惧害 BD-09: 29.1965172  119.476936


鐧惧害BD-09  杞� 鐏槦GCJ-02 杞�  鍦扮悆WGS-84
鐧惧害 BD-09: 29.196518  119.476936
鐏槦GCJ-02: 29.1908195  119.470342
鍦扮悆WGS-84: 29.1934702  119.465265

浠ヤ笂鏄緭鍑虹粨鏋滐紝浣跨敤鐧惧害API鍦板浘鍙栫殑鐐癸紝鑳借浆鍒癢GS-84鍧愭爣锛屽湪 maps.google.com涓婂湴鍥惧搴斻�� 
Google鍦板浘涓浗鐗堬紝鏂逛究鎶婅緭鍏ュ嚑涓伀鏄熷潗鏍囷紝閫氳繃濡備笅鏂瑰紡杩炴帴璧锋潵锛�%09鏄浆涔夌
http://www.google.cn/maps/dir/29.1934702%09119.465265/29.1908196%09119.470341/29.1965172%09119.476936/

```
	鐩稿叧閾炬帴
	https://github.com/hongwenjun/nmea_gprmc
	
	https://github.com/hongwenjun/TrajectoryCombine

 
>>>>>>> a283afdc88a6d5e5feb97cbdd1c97c4304217d55
