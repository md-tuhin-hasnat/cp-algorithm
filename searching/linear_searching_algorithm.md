# ১. লিনিয়ার সার্চিং অ্যালগরিদম

## ১.১ পরিচিতি

মনে কর তোমাকে একটা সংখ্যার অ্যারে `{১০,১৩,১৭,১৯,২৩} `দেওয়া হল। এখন তোমাকে বলা হল কোন একটা সংখ্যা `১৯` কে খুঁজে বের করতে হবে। তুমি সেই সংখ্যাকে কিভাবে খুঁজে বের করবে?

**এই প্রশ্নের উত্তর বেশিরভাগ মানুষ যেভাবে দিবে তা হলোঃ**

* প্রথম থেকে চেক করতে করতে যাবে
* যখনই ১৯ পেয়ে যাবে তখনই থেমে যাবে

**যেমনঃ**

1. অ্যারের প্রথম সংখ্যা চেক করবে। প্রথম সংখ্যাটি হলো ১০, যা ১৯ নয়।
2. অ্যারের দ্বিতীয় সংখ্যা (১৩) চেক করবে, যা ১৯ নয়।
3. অ্যারের তৃতীয় সংখ্যা (১৭) চেক করবে, যা ১৯ নয়।
4. অ্যারের চতূর্থ সংখ্যা (১৯) চেক করবে, যা ১৯ এর সমান। সুতরাং আর পরবর্তী সংখ্যা চেক করার দরকার নেই। আমরা আমাদের কাঙ্ক্ষিত সংখ্যা পেয়ে গিয়েছি।

> আমরা এতক্ষণ যে process নিয়ে আলোচনা করলাম এইটাই লিনিয়ার সার্চ।
## ১.২ ব্যাবহার

লিনিয়ার সার্চ হলো সব থেকে সহজ এবং সিম্পল সার্চ টেকনিক। যদিও এর টাইম কম্পেক্সিটি তুলনামূলকভাবে বেশি, তারপরও এর ব্যবহার লক্ষণীয়। আমরা লিনিয়ার সার্চ টেকনিক ব্যবহার করি যদিঃ

* অ্যারের সাইজ যদি খুব বেশি না হয়।
* সহজ ইমপ্লিমেন্টেশন যদি মুল লক্ষ্য হয়।
* অ্যারে যদি ক্রমান্বয়ে (**সর্টেড**) সাজানো না থাকে।
## ১.৩ অ্যালগরিদম

1. অ্যারের ইনডেক্স বাই ইনডেক্স চেক করতে হবে যে ওই ইনডেক্স এর সংখ্যাটি আমাদের কাঙ্ক্ষিত সংখ্যা কিনা।
2. যদি সংখ্যাটি কাঙ্ক্ষিত সংখ্যা হয় তাহলে আমরা ইনডেক্সকে সলিউশন বলতে পারি।
3. যদি অ্যারের সব ইনডেক্স চেক করেও কোন সংখ্যা কাঙ্ক্ষিত সংখ্যার সাথে না মিলে তার মানে সংখ্যাটি অ্যারেতে নেই।

## ১.৪ স্যুডোকোড

```python
function linearSearch(arr, target):
    for i from 0 to length(arr) - 1:
        if arr[i] == target:
            return i
    return -1

```

## ১.৫ ইমপ্লিমেন্টেশন

**C++ ইমপ্লিমেন্টেশনঃ**

```cpp
#include <bits/stdc++.h>
using namespace std;

// নিচের ফাংশনটি একটি অ্যারে এবং একটি টার্গেট ভ্যালু প্যারামিটার হিসেবে নেয় এবং টার্গেট ভ্যালু কত নম্বর ইনডেক্স এ আছে তা রিটার্ন করে
int linearSearch(vector<int> &arr,int target){
  int sizeOfArray = arr.size();

  for(int index = 0; index<sizeOfArray; ++index){
    if(arr[index] == target){
      return index;
    }
  }
  
  return -1;
}

//driver codes
int main(){

  vector<int>arr = {10,13,17,19,23};
  int index = linearSearch(arr,19);

  if(index == -1){
    cout<<19<<" is not present in the array\n";
  }
  else{
    cout<<"The index of "<<19<<" is "<<index<<"\n";
  }
}
```

## ১.৬ কমপ্লেক্সিটি

| কেস                                                                                                             | টাইম কমপ্লেক্সিটি |
| :----------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| বেস্ট কেস (টার্গেট অ্যারের প্রথম ইনডেক্স এ আছে)                              | O(1)                              |
| ওরস্ট কেস (টার্গেট অ্যারেতে নেয় অথবা অ্যারের শেষ ইনডেক্স এ আছে) | O(n)                              |
| এভারেজ কেস                                                                                                | O(n/2) = O(n)                     |

## ১.৭ উপকারিতা এবং অপকারিতা

**উপকারিতাঃ**

* [X] অ্যারে ক্রমান্বয়ে সাজানো না থাকলেও কাজ করে
* [X] সিম্পল এবং সহজ ইমপ্লিমেন্টেশন
* [X] স্পেস কমপ্লেক্সিটি **o(1)**

**অপকারিতাঃ**

* [ ] টাইম কমপ্লেক্সিটি তুলনামূলক বেশি
