---
title: code-test.md
date: 2018-08-15 11:46:17
tags:
---

````c
#include<map>
#include<string>
#include<iostream>
using namespace std;

void print(map<int, string>& mapStu, int nValue)
{
    cout << "mapStu" << nValue << "数据信息：" << endl;
    cout << "size: " << mapStu.size() << endl;
    map<int, string>::iterator iter = mapStu.begin();
    for (; iter != mapStu.end(); ++iter)
    {
        cout << "key: " << iter->first << " value: " << iter->second << endl;
    }
    cout << endl;
}

int main()
{
    map<int, string> mapStu1;
    typedef map<int, string> mapType;
    mapType mapStu2, mapStu3, mapStu4;

    mapStu1.insert(map<int, string>::value_type(1, "Qin"));
    mapStu1.insert(map<int, string>::value_type(2, "Sun"));
    mapStu1.insert(map<int, string>::value_type(3, "Wang"));
    mapStu1.insert(map<int, string>::value_type(2, "Zhao"));
    print(mapStu1, 1);
    mapStu2.insert(pair<int, string>(1, "Qin"));
    mapStu2.insert(pair<int, string>(2, "Sun"));
    mapStu2.insert(pair<int, string>(3, "Wang"));
    mapStu2.insert(pair<int, string>(2, "Zhao"));
    print(mapStu2, 2);
    mapStu3.insert(make_pair<int, string>(2, "Sun"));
    mapStu3.insert(make_pair<int, string>(3, "Wang"));
    mapStu3.insert(make_pair<int, string>(2, "Zhao"));
    print(mapStu3, 3);
    mapStu4[1] = "Qin";
    mapStu4[2] = "Sun";
    mapStu4[3] = "Wang";
    mapStu4[2] = "Zhao";
    print(mapStu4, 4);

    pair<map<int, string>::iterator, bool> iter_pair;
    iter_pair = mapStu1.insert(map<int, string>::value_type(3, "Li"));
    cout << "插入成功与否：" << iter_pair.second << endl;

    return 0;
}
````
