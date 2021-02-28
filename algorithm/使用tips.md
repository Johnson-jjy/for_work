## 刷题常用API

- **Integer类**

  - ​	

    ```Java
    //进制转换
    	Integer.toString(int n,int radix);//十进制转radix进制
    	Integer.parseInt(String n,int radix);//radix转十进制（返回int）
    	Integer.toOctalString()/toHexString()//8/16进制
    //
        Integer.valueOF(int);//返回包装类Integer
    	Integer.parseInt();//返回基本类型
    ```

- **String类**

  - ```java
    str.replaceAll("a","b");//字符串替换
    str.split(",");//字符串分割
    char[] charStr=str.toCharArray();//String-》char
    str.charAt(index)://String-》char
    str.substring(start,end);//字符串字串，包含start，不包含end
    str.indexOf(int ch);//返回字符ch第一次出现的索引
    ```

- **HashMap**

  - ```java
    map.containskey(Object key);//判断是否包含key值
    map.containsValue(Object value);//包含返回true
    
    map.entrySet().iterator();//遍历
    
    Iterator<Map.Entry<Integer, Integer>> i = map.entrySet().iterator();
      while(i.hasNext()) {
       Entry<Integer, Integer> en = (Entry<Integer, Integer>) i.next();
       int key = (int )en.getKey();
       int value = (int) en.getValue();
       System.out.println(key + ", " + value);
      }
    
    Set<Integer> times = new HashSet<Integer>();
    for (Map.Entry<Integer, Integer> x : occur.entrySet()) {
        times.add(x.getValue());
    }
    
    
    map.get(Object key);//获得指定key值对应键值
    map.put(K key,V value);//将键值对《K，V》放入map。map.putAll()
    
    map.remove(Object key);//删除指定键值
    map.clear();//移除所有
    
    map.equals(Object o);//比较指定的对象与此映射是否相等
    map.hashCode();//返回此映射的哈希码值
    map.isEmpty();//未包含映射关系，返回true
    map.size();//返回此映射中的键-值映射关系数
    
    map.values();//返回此映射中包含的值的Collection视图
    
    for (int x : arr) {
    	map.put(x, map.getOrDefault(x, 0) + 1);
    }
    ```

  ****

- **Iterator**

  - ```java
    hasNext();//如果迭代器中还有元素，则返回true
    next();//返回迭代器中的下一个元素
    remove();//删除迭代器新返回的元素
    ```

    

- **Scanner**

  - ```java
    Scanner scanner=new Scanner(System.in);//Scanner是一个扫描器，从键盘输入的数据，先存到缓存区等待读取。
    scanner.hasNext();//判断是否还有输入
    scanner.next()/nextInt();//接受下一个String/Int。判断读取结束的标识空白符：空格，回车，tab等等。next（）方法读取到空白符就结束；读取空格要用  
    nextline()或
    BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
    //使用BufferedReader对象的readLine()方法必须处理java.io.IOException异常（Exception）
    scanner.close();//用完关闭
    ```

    

- **Arrays**

  - ```java
    Arrays.sort(arr);//排序基本对象类型（不可以是基本数据类型，int要转化为Integer），采用双轴快排实现，即两个基准元素。默认是升序，可重写Comparator()匿名内部类的compare()方法，重新定义排序规则。
    Arrays.sort(arr,1,3);//给第1位（0开始）到第3位（不包括）排序
    
    //定义规则：对字符串合并后的结果排序，升序。
    Arrays.sort(str, new Comparator<String>(){
    	public int compare(String s1, String s2){
    		String a = s1 + s2;
    		String b = s2 + s1;
    		return a.compareTo(b); //a>b，返回大于0；a<b，返回小于0；相等返回0
    	}
    });
    
    Arrays.fill(arr,2);// 2 2 2 2 2
      Arrays.fill(arr,1,3,8);// 0 8 8 0 0
    
      Arrays.equals(arr1,arr2);//如果是arr1.equals(arr2),则返回false，因为equals比较的是两个对象的地址，不是里面的数，而Arrays.equals重写了equals，所以，这里能比较元素是否相等。
    
      Arrays.binarySearch(arr,20);//能找到该元素，返回下标为1（0开始）
      Arrays.binarySearch(arr,35);//找不到元素，返回-x，从-1开始数，如题，返回-4 
      Arrays.binarySearch(arr,0,3,30);//从0到3位（不包括）找30，找到了，在第2位，返回2 
      Arrays.binarySearch(arr,0,3,40);//从0到3位（不包括）找40，找不到，从-1开始数，返回-4
    
      Arrays.copyOf(arr,3);//截取arr数组的3个元素赋值给姓数组arr1
      Arrays.copyOfRange(arr,1,3);//从第1位（0开始）截取到第3位（不包括）
    
    ```
    ```
    
    
    ```

- **Stack**

  - ```java
    stack.push(Object o);//入栈
    stack.pop();//出栈
    stack.peek();//返回栈顶
    stack.empty();//栈空
    stack.search(Object o);//返回对象在堆栈中的位置
    ```
  ```
    
    
  ```

- **Queue**

  - Queue接口，实现类常用LinkedList

  - ```java
    queue.add(E e);queue.offer(E,e);//在队尾添加元素，当容量已满时，add（）方法会抛出iLLegalStateException异常，offer（）方法只会返回false
    queue.remove();queue.poll();//都是返回队头元素，并在队列中删除返回的对象。不同点：如果没有元素remove（）会直接抛出NoSuchElementException异常，而poll（）会返回null
    queue.element();queue.peek;//返回但不删除队列头
    //add()和remove()方法在失败的时候会抛出异常（不推荐）

    ```
    
  
- **List**

  - ```java
    List<> a=new ArrayList<>();
    list.size();//返回list大小
    list.isEmpty();//判空
    list.contains(Object o);//判是否包含o
    list.indexOf(Object o);//正相查找，返回元素索引值
    list.lastIndexOf(Object o);//反向查找，返回元素索引值
    list.get(int index);//获取index位置的元素
    list.add(Object o);//将o添加到元素末尾
    list.remove(int index);//删除指定位置元素
    list.clear();//清空所有
    list.addAll();//添加所有
    ```

  
  
- **Deque**

  下表总结了上述 12 种方法：

  |          | **第一个元素 (头部)** | **最后一个元素 (尾部)** |              |              |
  | -------- | --------------------- | ----------------------- | ------------ | ------------ |
  |          | *抛出异常*            | *特殊值*                | *抛出异常*   | *特殊值*     |
  | **插入** | addFirst(e)           | offerFirst(e)           | addLast(e)   | offerLast(e) |
  | **删除** | removeFirst()         | pollFirst()             | removeLast() | pollLast()   |
  | **检查** | getFirst()            | peekFirst()             | getLast()    | peekLast()   |

  Deque接口扩展了 Queue 接口。在将双端队列用作队列时，将得到 FIFO（先进先出）行为。将元素添加到双端队列的末尾，从双端队列的开头移除元素。从 Queue 接口继承的方法完全等效于 Deque 方法，如下表所示：

  | **Queue方法** | **等效Deque方法** |
  | ------------- | ----------------- |
  | add add(e)    | addLast(e)        |
  | offer(e)      | offerLast(e)      |
  | remove()      | removeFirst()     |
  | poll()        | pollFirst()       |
  | element()     | getFirst()        |
  | peek()        | peekFirst()       |

  双端队列也可用作 LIFO（后进先出）堆栈。应优先使用此接口而不是遗留 Stack 类。在将双端队列用作堆栈时，元素被推入双端队列的开头并从双端队列开头弹出。堆栈方法完全等效于 Deque 方法，如下表所示：

  | **堆栈方法** | **等效Deque方法** |
  | ------------ | ----------------- |
  | push(e)      | addFirst(e)       |
  | pop()        | removeFirst()     |
  | peek()       | peekFirst()       |



#### 注释

1. crtl+/（单行）
2. crtl+shift+/（可多可单）
3. /+ * + * （函数块前，推荐）

#### 缩进

crtl+alt+i

#### 继承





### String、StringBuffer、StringBuilder

1.String、StringBuffer、StringBuilder的区别 https://zhuanlan.zhihu.com/p/77614811

2.参加了这么多面试，还是不懂StringBuffer和StringBuilder的区别？https://mp.weixin.qq.com/s/dltB1Fzwdezs4PDN8Thx6w

3.[StringBuilder类的作用，以及与String类的相互转换](https://www.cnblogs.com/chichung/p/10185560.html)





#### Java创建自定义类的对象数组

1. https://www.cnblogs.com/liuhuijie/p/9051896.html

其实也就是创建了数组后还要初始化。





#### 对相同内容修改--idea

shift+F6



#### 遍历ArrayList的四种方法

https://www.cnblogs.com/vansjun/p/7535352.html

迭代器，get（i）（for循环+get（i）的复杂度很高）



#### for循环中break与continue

break跳出整个循环，continue跳出此次循环--但还是要执行i的相关操作



#### 二维数组的行列数

```java

//定义一个整型数组:3行4列
int a[][] = new int[3][4];
//获取行数---3行
int lenY = a.length;
//获取列数---4列
int lenX = a[0].length;
```





#### 更新显卡驱动

https://www.yunqishi.net/video/14990.html

1.进入设备管理器

2.右键单击显卡选择更新驱动

3.选择自动搜索更新



#### Java输出空数组

```java
if (row==0){//此为输出空数组的方法
    int[] zero=new int[0];
    return zero;
}
```