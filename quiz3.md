1. 請解釋 ```database.yml```, ```routes.rb```, 和 ```Gemifle``` 分別是什麼？ 他們分別在一個 Rails 專案裡的什麼位置？ 他們為什麼對一個 Rails 專案如此重要？
  
  ```ruby
  database.yml ：在config內,rails專案設定database的地方
  routes.rb : 在config內,設定整個rails專案路由的地方
  Gemfile : 在根目錄內,記錄rails專案裡使用了哪些library
  ```

2. MVC 架構裡的 M, V, 和 C 分別代表什麼？
   ```ruby 
   M = Model 和database上某個資料表對應
   V = View 呈現及提供使用者操作介面
   C = Controller 處理前端的action
   skinny controller, fat model
   ```

3. 請解釋 CRUD 是哪四個字的縮寫？ 
   ```ruby 
   C = Create 新增資料
   R = Read   讀取資料
   U = Update 更新資料
   D = Destroy刪除資料

   ```

4. 請問在 routes.rb 裡面加入以下程式碼會產生出哪一些 url？ (提示：在 browser 輸入```http://localhost:3000/rails/info/routes```)
	```ruby
	resources :users
	```
    ```ruby 
    產出CRUD的URL

    ```

5. 請解釋 model 檔案和 migration 檔案的差別

   ```ruby 
   model :對應資料庫裡的某個資料表
   migration ：更改資料庫現有的狀態,ex:資料庫欄位的控制

   ```
6. 若今天發現一個 migration 檔寫錯，請問我應該用什麼指令回復到上一個版本的 migration? 

   ```ruby 

   rake db:rollback

   ```

7. 假設今天
	* 我要在資料庫裡產出一個叫 group 的資料表
	* 裡面包括的欄位名稱和相對應的資料型別是： 
		**name (string)**,
		**description (text)**,
		**members (integer)**
    * 請寫出一個能產生出以上需求的 migration 檔

    ```ruby 
    rails g migration add_group_table

    class AddGroupTable < ActiveRecord::Migration
      def change
        create_table :groups do |t|
          t.string :name
          t.text :description
          t.integer :member
          t.timestamps
        end
      end
    end

    ```

8. 請解釋什麼是 ActiveRecord? 

   ```ruby 
   rails的核心原件,保護開發者不用再花時間寫SQL,只要用ruby語法就可以對SQL進行操作,像是翻譯器,翻譯ruby和SQL語言

   ```



