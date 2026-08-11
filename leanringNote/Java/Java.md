
引用相等："=="
    "=="比较的是两个变量是否指向内存的同一个对象
    ```Java
        String a = new String("hello");
        String b = new String("hello");
        System.out.println(a == b);  // false — 堆里是两个不同的对象

    ```
对象相等：equals（）
    "equals()"比较的是两个对象在逻辑上是否相等
    ```Java
        String a = new String("hello");
        String b = new String("hello");
        System.out.println(a.equals(b));  // true — String 重写了 equals，比较字符序列
    ```
>特殊情况:字符串常量池
>Object类 如果没有重写equals()方法，将退化为"=="


String、StringBuilder、StringBuffer
String：不可变长 线程安全 拼接时产生大量临时对象 底层实现：final byte[] 
StringBuilder:可变长 线程不安全 快 继承AbstractStringBuilder，可扩容
StringBuffer：可变长 线程安全 相StringBuilder来说较慢 继承AbstractStringBuilder，可扩容

>StringBuilder、StringBuffer最常用的场景大多数与字符串拼接（需要.append()）相关
>算法竞赛中：经常在需要频繁的进行字符串拼接以及需要每一步都需要修改字符串（利用"可变长的"特性）
>删除字符串中相邻重复项

字符串拼接场景：
    ```Java
        String s1 = "hello";
        String s2 = "World";
        String s3 = s1 + s2 
        System.out.println(s1 + "," + "s2")
    ```
    ```Java
        String name = "张三"
        int age = 25;
        String info = "姓名：" + name + ",年龄：" + age;

        String info = new StringBuilder().append("姓名：").append(",年龄：").append(age).toString;
    ```

    常用用法：
    ```Java
        StringBuilder sb = new StringBuilder();
        for(int i = 1; i <= 10000;i++){
            sb.append(i);
        }
        String result = sb.toString;
    ```

遍历map集合的两种不同方式：
    方式一：通过map.keySet()获取map的所有键，并将其赋值给创建的Set集合对象，通过增强型for循环遍历Set集合。再在循环体中取出键所对应的值。
    ```java
        import java.util.*;
        public class maploop{

            
            public static void main(String args[]){
                Map<String,String> map= new HashMap<String,String>;
                map.put("一号"，"张三");
                map.put("二号"，"李四");

                //利用Set集合获取map集合的所有键
                Set<String> keys = map.keySet();

                //增强型for循环
                for(String key : keys){
                    String value = map.get(key);
                    System.out.println(key + ":" + value);
                }
            }
        }

    ```
    方式二：通过map.entrySet()获取map的所有键值对
    ```java
        import java.util.*;
        public class maploop{

            
            public static void main(String args[]){
                Map<String,String> map= new HashMap<String,String>;
                map.put("一号"，"张三");
                map.put("二号"，"李四");

                //利用Set集合获取map集合的所有键
                Set<Map.Entry<String,String>> entries = map.entrySet();

                //增强型for循环
                for(Map.Entry<String,String> entry : entries){
                    String key = entry.getKey();
                    String value = entry.getvalue();
                    System.out.println(key + ":" + value);
                }
            }
        }
    ```


