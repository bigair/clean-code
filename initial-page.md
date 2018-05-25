---
description: 寫出容易了解的函式
---

# 函式

## 簡短！

## 只做一件事情

### 降層準則

由上而下閱讀程式碼

## Switch 敘述

保持以下原則：單一職責原則、開放閉合原則

多形的情況，可以用工廠模式 \(Factory pattern\) 來處理

```php
<?php
/**
 * 抽象"烹煮"類別
 */
abstract class Cook {
    // 準備食材
    public abstract function prepareIngredient();
    // 烹煮食材
    public abstract function cooking();
    // 上菜
    public abstract function serve(); 
}
?>
```

想吃咖哩

```php
<?php
/**
 * 咖哩
 */
class Curry extends Cook
{   
    // 準備食材
    public function prepareIngredient()
    {
        echo "準備「馬鈴薯」、「蘿蔔」、「洋蔥」、「肉」\n";
    }

    // 烹煮食材
    public function cooking()
    {
        echo "下鍋炒肉，等肉熟之後，將「馬鈴薯」、「蘿蔔」、「洋蔥」加到鍋裡並加滿水，等水滾加入咖哩塊悶熟即可\n";
    }

    // 上菜
    public function serve()
    {
        echo "盤子放上白飯，將咖哩淋在白飯周圍即可\n";
    }
}

$curry = new Curry;
$curry->prepareIngredient();    // 準備食材
$curry->cooking();              // 烹煮食材
$curry->serve();                // 上菜
?>
```

## 使用具描述能力的函式名稱

動詞與關鍵字能更好理解函式的用意，預期函式的輸入參數、輸出參數型態

```php
set()
get()
has()
is()
enable()
```

## 函式的參數

參數的數量？

### 輸入型的參數

任何迫使你要回去查看函式署名的情況，都等同於「再三檢查」，盡量避免

## 指令與查詢的分離

```php
if (set("username", "limit")) ...
```

取代

```php
if (attributeExists("username")) {
    setAttribute("username", "limit");
}
```

## 不要重複自己

## 避免使用巢狀迴圈

```php
if ($a == E::OK) {
    if ($b == E::OK) {
        if ($c == E::OK) {
            ....
        }
    }
}
```

可以改寫為

```php
if ($a != E::OK) {
    return false;
}

if ($b != E::OK) {
    return false;
}

if ($c != E::OK) {
    return false;
}
```

## 使用例外處理取代回傳錯誤碼

### 錯誤處理就是一件事



