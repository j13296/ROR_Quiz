1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異

Fixnum(整數)：可以被整除,只會取整數
Float(浮點數)：帶有小數的數值 3.to_f / 4 =>0.75

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```

第一種：會造成記憶體上不必要的浪費
第二種：字串內插的方法可避免記憶體浪費的問題

3. 請解釋 array 和 hash 的不同處

array（陣列）: 有排序過的清單,可以含很多不同類別的資料在裡面
hash: 用key可找出相對應的value

4. 請寫一段 code 從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值

```ruby
arr.select {|x| x.class != String }
arr.reject {|x| x.class == String }
```

5. 請列出兩種產出亂數的方法

```ruby
rand(1..3)
[1,2,3].shuffle!.last
```

6. 請把 lesson1 程式碼裡的 calculator.rb 裡面的使用者輸入兩個數字的方式改寫成 method，並要有防止使用者亂輸入值的功能

```ruby
def firstNumber()
        begin
            puts "Please enter the first number:"
            num1 = gets.chomp.to_i
        end while !(num1.class == Fixnum)
        num1
    end

    def secondNumber()
        begin
            puts "Please enter the second number:"
            num2 = gets.chomp.to_i
        end while !(num2.class == Fixnum)
        num2
    end
```


7. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果

  => false && true || true
  => false || true
  => true

8. 請問 binding.pry 是什麼？ 要如何使用它？

程式開頭輸入require 'pry' 
binding.pry 放在程式有問題的地方,以便檢查程式發生錯誤的地方在哪裡

9. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```

  簡化後：
  ```ruby
  var = 5
  var >= 5 ? "var is greater than or equal to 5" : "var is less than 5"



