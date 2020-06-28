## 基本寫法
> PHP在執行的時候，內容前後要包住 ```<?php``` 內容 ```?>``` ，這樣才會執行。

> 先從最簡單最原始的的印出Hello World開始

```php
<?php 
    echo "Hello World";
    /*
    1. echo是顯示
    2. 要印出的文字用雙引號””包住
    3. 每句語法最後用;隔開
    */
?>
```

## 註解寫法
> // 單行註解

> /* 區塊註解、多行註解，中間的內容都會是註解狀態 */

```php
<?php
    // 單行註解
    /* 
    區塊註解、多行註解
    中間的內容都會是註解狀態
    echo "就算是寫php語法，也是註解狀態"
    */
?>
```

## 變數
> 在php 中的變數與大多數的的程式語言變數一樣，是某些資料的容器，會存放在記憶體中的某處。

> 以「$」來識別，再將資料指定給變數，提供程式後續的引用其內存的資料。

> 有幾點需要注意：
> - 變數名稱有大小寫之分，所以 $abc、$ABC、$Abc、$aBc之類的都算是不一樣的變數
> - 變數的開頭必須是英文字母或是底線”_”，不能是數字或其他字元
> - 變數名稱不能有空白，可以用_來做連接。例： $my_account
> - 一些像是php已經定義的關鍵字不可以在定義為變數名稱。例： $array是違法的
```php
<?php
    $var = "小叮噹";
    $Var = "大雄";
    echo "$var, $Var";  // 會輸出 小叮噹, 大雄

    $4site = '胖虎';    // 錯誤，因為開頭是數字
    $_4site = '小夫';   // 正確，開頭是底線
?>
```
> PHP語法的變數有一個特點，不管是整數、浮點數、字串、陣列、布林值，都是以$XXX作為變數宣告，這是**弱型別**的一個特色。

## 常數
> 常數也是存放資料的變數，只不過是給予資料之後，就不可改變資料內容。

> 常數是用 define( )函數來建立。
```php
<?php
    define("PI", "3.1415926");
    echo PI;  // 輸出3.1415926
?>
```

## 資料型態 Data Type
> - 布林值(boolean)：TRUE 或 FALSE
> - 整數(integer)
> - 浮點數(float)：包括 floats 、 doubles 或 real numbers
> - 字串(string)：分別用單引號或雙引號來定義。
>   - 單引號：指定一個簡單字串的最簡單的方法是用單引號(字元 ' )
>   - 雙引號：以雙引號(字元 " )圍住的字串，PHP會對該字串做「變數置入」的動作。
```php
<?php
    $name = "大雄";
    echo '姓名: $name';     // 顯示 姓名: $name
    echo "姓名: $name";     // 顯示 姓名: 大雄
?>
```
> 特殊字元

|跳脫字元|用途|
|:---:|---|
|\n|換行|
|\r|游標回頭|
|\t|Tab|
|\\|\符號|
|\"|"符號|
|\$|$符號|

## 運算子 Operator
> 先舉個例子

$total = $a + $b;

> $a + $b 稱為「表示式」(expressions)
> <br>
> ```+``` 即稱為運算子(operator)

- 算術運算子
> ```+```<br>
> ```-```<br>
> ```*```<br>
> ```/```<br>
> ```%```<br>

- 指定運算子
> ```=```<br>
> 實際上意味著把**右邊**運算式的值**指定給左邊**運算數。<br>
> Ex. $a = $a + 2;

- 加一／減一運算子

    |||
    |:---:|---|
    |++$a|$a 的值加一，然後傳回$a 的值|
    |$a++|傳回$a 的值，然後將$a 的值加一|
    |--$a|$a 的值減一， 然後傳回$a 的值|
    |$a--|傳回$a 的值，然後將$a 的值減一|

- 邏輯運算子

    |||
    |:---:|---|
    |and AND &&|和|
    |or OR ```||```|或
    |XOR|互斥|
    |!|非|

- 比較運算子

    |||
    |:---:|---|
    |==|等於|
    |===|等於、且類型相同|
    |!=|不等於|
    |<|小於|
    |>|大於|
    |<=|小於等於|
    |>=|大於等於|

- 字串運算子

    |||
    |:---:|---|
    |.|連接符號|
    |.=|Ex. $c .= “123”; 相當於 $c = $c . “123”;|

- 陣列運算子

    |||
    |:---:|---|
    |+|把右邊的陣列附加到左邊的陣列後，但是重複的索引值不會被覆蓋。|
```php
    <?php
        $a = array("1" => "一月", "2" => "二月");
        $b = array("1" => "星期一", "2" => "星期二", "3" => "星期三");
        $c = $a + $b;
        // $c的內容為array([1]=>"一月", [2]=>"二月", [3]=>"星期三")
    ?>
```

## 函數 Function
> 將常用的流程或者變數等元件，組織成一個固定的格式，以便調用及簡化程式。

基本格式
```
function foo ($arg_1, $arg_2, ..., $arg_n) /* foo函數名；$arg傳入參數*/

{

echo "Example function.\n"; // 程式動作

return $retval; // 傳回結果

}
```
```php
<?php
    function circle_len($r)
    {
        $result = $r * 2 * 3.14;
        return $result;
    }

    $r = 10;
    echo "圓周長 = " . circle_len($r);  // 輸出 圓周長 = 62.8
?>
```

## 陣列 Array
> 有順序性的Map資料結構，所以他不只可以作為一般的陣列使用外，搭配相關函式還可以將他作為各種資料結構使用。

> 陣列中的元素也可以是陣列，而成為多維陣列的應用。

> 基本上陣列key都是從0開始排列。
```php
<?php
    $arr = array();
    $arr[] = 55;        // 自動指派索引, $ar[0]
    $arr[4] = 60;       // 指定到key為4的位置
    $arr[‘value’] = “Hello World”;  // key也可以是自訂的字串

    echo $arr[0];       // 顯示55
    print_r($arr);      // 顯示 Array ( [0] => 55 [4] => 60 [value] => Hello World )
?>
```

## 物件 Object
> 物件使用new關鍵字來建立，物件一般由類別(Class)來定義內容，也可以使用基本的物件類別stdClass。
```php
<?php
    class A {
        public $M = 10;
        function F() {
            echo "Hello";
        }
    }
    
    $a = new A();   // 或者簡寫為 $a = new A;
    echo $a->M;     // 10
    $a->F();        // Hello
    print_r($a);    // A Object ( [M] => 10 )
    
    $obj = new stdClass;
    print_r($obj);  // stdClass Object ( )
    $obj->x = 1;
    $obj->y = 2;
    print_r($obj);  // stdClass Object ( [x] => 1 [y] => 2 )
?>

```

## 條件判斷
> 滿足某個條件，就去做某件事。
> <br>
> 想要執行某些動作，必須符合某些條件。

> 條件判斷經常使用，在程式中，並不會永遠從第一行執行到最後一行，加入判斷能使程式更通用。

- if...else
```php
基礎語法
if(判斷式) {
    ...
}
elseif(判斷式) {
    ...
}
else {
    ...
}
```

```php
<?php
    if($weather == "rainning") {
        echo "bring an umbrella";
        echo "wear rain boots";
    }
    else {
        echo "yeah~~~~happy";
    }
?>
```

- Switch-case
> 判斷的內容如果是多種結果，可以使用switch-case的方式來寫判斷條件
```php
基礎語法
switch(表示式){
    case 匹配1：
        當匹配1和表示式匹配成功執行的程式碼;
        break;

    case 匹配2：
        當匹配2和表示式匹配成功執行的程式碼;
        break;

    default：
        如果case語句沒有與表示式成功所執行的程式碼;
}
```

```php
<?php
    switch($week){
        case "Sunday"：
            echo "星期日";
            break;

        case "Monday"：
            echo "星期一";
            break;

        case "Tuesday"：
            echo "星期二";
            break;
        
        case "Wednesday"：
            echo "星期三";
            break;

        case "Thursday"：
            echo "星期四";
            break;
        
        case "Friday"：
            echo "星期五";
            break;
        
        case "Saturday"：
            echo "星期六";
            break;

        default：
            echo "語法錯誤";
    }
?>
```

## 迴圈
> 重複性的語法內容，利用迴圈來減少撰寫時間及後續維護工作，程式也更為簡潔

- for
```php
<?php
    for($i = 0; $i < 10; $i++) {
        echo $i;
    }

    /* 輸出：0 1 2 3 4 5 6 7 8 9 */
?>
```

- foreach
```php
<?php
    $i = array(0, 1, 2, 3, 4, 5, 6, 7, 8, 9);

    foreach($i as $value) {
        echo $value;
    }

    /* 輸出：0 1 2 3 4 5 6 7 8 9 */
?>
```

- while
```php
<?php
    $i = 0;

    while($i < 10) {
        echo $i;
        $i++;
    }

    /* 輸出：0 1 2 3 4 5 6 7 8 9 */
?>
```

## 參考資料
[寫給朋友的 PHP 從 0 到 100 實戰教程](https://ithelp.ithome.com.tw/users/20107394/ironman/1332?page=1)

[PHP 基礎教學](https://progressbar.tw/serials/1)