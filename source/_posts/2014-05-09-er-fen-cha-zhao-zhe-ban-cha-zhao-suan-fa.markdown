---
layout: post
title: "二分查找(折半查找)算法"
date: 2014-05-09 12:58:00 +0800
comments: true

categories: 数据结构 
---
*****
**二分查找**，也称**折半查找**算法，是一种在有序数组中查找某一特定元素的搜索算法。搜素过程从数组的中间元素开始，如果中间元素正好是要查找的元素，则搜素过程结束；如果某一特定元素大于或者小于中间元素，则在数组大于或小于中间元素的那一半中查找，而且跟开始一样从中间元素开始比较。如果在某一步骤数组为空，则代表找不到。这种搜索算法每一次比较都使搜索范围缩小一半。<!--more-->

* 复杂度分析 <br>
   * 时间复杂度<br>
    
     折半搜索每次把搜索区域减少一半，时间复杂度为O\left( \log n  \right)。（n代表集合中元素的个数）

  * 空间复杂度<br>
  
    O(1)。虽以递归形式定义，但是尾递归，可改写为循环。<br>
    
 * 优点<br>
  
   比较次数少，查找速度快，平均性能好
 
 * 缺点<br />
 
   要求待查表为有序表，且插入删除困难
   
   因此，折半查找方法适用于不经常变动而查找频繁的有序列表。<br >
  
  <p style="color:blue">代码示例<p><b/>

* Objective-C 源代码   <br>		
					
					findArray = @[@1, @2, @3, @4, @5, @6, @7,@8, @9, @10];
                    NSInteger findObject = 2;
                    
                    //数组下标
                    int mid = 0;
                    int min = 0;
                    int max = (int)(findArray.count - 1);
                    
                    while (min <= max) {
                        mid = (min + max)/2;
                        NSInteger midObject = [[findArray objectAtIndex:mid] integerValue];
        
                        if (findObject == midObject) {
                            NSLog(@"The index of the findObject is: %d", mid);
            
                            return;
                        }
                       else if(findObject > midObject){
                            min = mid + 1;
                            max = max;
                       }
                      else{
                           min = 0;
                           max = max - mid - 1;
                      }
                   }

                    
* C 源代码<br >
 							

		 int findArray[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    	 int findObject = 10;

    	//数组下标
    	int mid = 0;
     	int min = 0;
    	int max = sizeof(findArray);
    
   	    while (min <= max) {
        mid = (min + max)/2;
        int midObject = findArray[mid];
        
        if (findObject == midObject) {
            printf("The index of the findObject is: %d", mid);
            
            return;
        }
        else if(findObject > midObject){
            min = mid + 1;
            max = max;
        }
        else{
            min = 0;
            max = max - mid - 1;
        }
      }

   
   
   
   
   