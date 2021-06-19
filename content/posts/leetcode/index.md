---
title: "Hello"
date: 2021-06-18T15:32:05+08:00
description: ""
categories: []
toc: false
dropCap: false
displayInMenu: false
displayInList: true
draft: false
resources:
- name: featuredImage
  src: "nyc.jpg"
  params:
    description: ""
    attribution:
      name: "Aether"
      link: ""
---
## 数组篇
描述：长度为n的数组，其中元素都在0-n-1之间，假设保证数组中存在重复元素，找出满足条件的一个元素.  
- 分析：  
	1. 暴力法遍历，时间复杂度O($n^2$)
	2. 哈希表记录，时间复杂度O($n$)
	3. 排序后查找
- show me code  
```cpp
#include<iostream>
#include<vector>
using namespace std;

int duplicate_1(vector<int>&);
int duplicate_2(vector<int>&);
int duplicate_3(vector<int>&);
int duplicate_4(vector<int>&);

int main(){
	vector<int>& numbers {1,2,3,5,4,5};
	int output = duplicate_1(numbers);
	cout << output << endl;		
}

int duplicate_1(vector<int>& numbers){ 
	for(int i=0; i<numbers.size(); i++){
		for(int j=0; j<numbers.size(); j++){
			if(numbers[j]==numbers[i] && j!=i){
				return numbers[j];
			}
		}
	}
	return -1; 
}
int duplicate_2(vector<int>& numbers){
	if(numbers.size()<2){
		return -1;
	}
	sort(numbers.begin(), numbers.end());
	for(int i=0; i<numbers.size(); i++){
		if(numbers[i+1] == numbers[i]){
			return numbers[i+1];
		}
	}
	return -1;
}

```



