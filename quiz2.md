1. 請用簡單的方式敘述以下每一行程式碼：

  ```ruby 
  a = 1            #設a的值為1
  @a = 2           #將instance variable（實例變數）@a設為2
  @@a = 5          #將class variable @@a設定為5
  user = User.new  #利用User為模板創造新物件user
  user.name        #讀取新物件user叫name的資料
  user.name = "Joe"#設定新參數為Joe,也就是讀取setter method的資料為Joe
  ```
2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?
   
   ```ruby
   module就是工具箱,可以直接利用module include進method裡

   module Knowledge
     def math
         puts 'I love math'
     end
   
   class Student
     include Knowledge
   end

   bob = Student.new
   bob.math

   ```

3. 請說明 class 和 instance variable 之間的差別
   
   ```ruby
   instance variable 綁定被模板造出來新物件的資料
   class variable 綁定class（模板）本身的資料

   ```

4. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是: 
  ```ruby
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method
 
  ```ruby
  class User
    attr_accessor :name, :gender, :job
    def initialize(name, gender, job)
        @name = name
        @gender = gender
        @job = job
    end
  end

  ```


5. self 在：
  a. class 裡，method 外面
  b. class 裡，instance method 裡
  分別是指向什麼?

  ```ruby 
  a.指class（模板）自己
  b.指被創造出來的物件
  ```


6. attr_accessor 的功能是什麼
  
  ```ruby
  利用ruby代勞,產生getter和setter的方法 
  ```


7. 請說明 public 和 private method 之間的不同

   ```ruby
   public method: 可以在產生新物件後直接使用
   private method: 只能在特定class裡被使用或是被呼叫

   ```


8. Ruby 是如何確保一個 module 的 method 會被 include 它的 class 使用到？ (提示：method lookup)

   ```ruby
   利用ancestors的方法查出最原始的物件,往上查找第一個有符合的這類別的方法,並使用它

   ```   
