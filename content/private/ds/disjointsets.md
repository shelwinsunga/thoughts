---
title: "Disjoint Sets"
enableToc: false
date: 2022-11-17
tags:
- 
- 
---


```
class DisjointSet {
    ArrayList<ArrayList<Integer>> nums = new ArrayList<ArrayList<Integer>>();
    
    public DisjointSet(int length){
        for(int i = 0; i < length; i++){
            ArrayList<Integer> num = new ArrayList<Integer>();
            num.add(i);
            nums.add(num);
        }
    }
    
    
    public void printSet(){
        System.out.print("{");
        for(int i = 0; i < nums.size(); i++){
            System.out.print("{");
            for(int j = 0; j < nums.get(i).size(); j++){
                if(j+1 >= nums.get(i).size()){
                    System.out.print(nums.get(i).get(j));
                } else {
                    System.out.print(nums.get(i).get(j) + ",");
                }
            }
            System.out.print("}");
        }
        System.out.println("}");
    }
    
    public void connect(int x, int y){
        for(int i = 0; i < nums.size(); i++){
            if(nums.get(i).contains(x)){
                nums.get(i).add(y);
                i++;
            } else if (nums.get(i).contains(y)){
                nums.remove(i);
            }
        }    
    }
    
    public boolean isConnected(int x, int y){
         for(int i = 0; i < nums.size(); i++){
             if(nums.get(i).contains(x) && nums.get(i).contains(y)){
                 return true;
             }
         }
         return false;
    }
    

    
    public static void main(String[] args){
        DisjointSet set = new DisjointSet(10);
        set.printSet();
        set.connect(1,3);
        set.printSet();
        System.out.println(set.isConnected(4,6));
        set.connect(3,7);
        set.printSet();
        System.out.println(set.isConnected(7,1));
        set.printSet();
        set.connect(2,7);
        set.printSet();
    }
    
}
```