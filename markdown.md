- git merge 問題
	- 本地分支: 含有wildfly 和weblogic 資料夾;主分支:只有主要資料夾
	- 當本地分支要與主分支合併時，會出現合併衝突，原因本地分之是已將舊版本上主要資料夾的檔案已經調整搬至wildfly和weblogic。而要合併的分支上主分支出現了已被搬動檔案進行修改,因此產生已被搬動檔案出現合併衝突。
	- 情境模擬
		- 本地(branch): 
		```
		└─f (like: wildfly/weblogic資料夾)
	        test.txt
		```
		- 主分支(branch):
		```
		test.txt
		```
		- test.txt 內容
		```
		// 本地
		12456
		
		// 主分支
		1234
		123
		123
		```
		- 模擬:
			- 在本地分之輸入cmd : `git merge <主分支>`
	- 可能遇到的問題
		- 執行完命令後出現 : `Merge made by the 'ort' strategy`
			- 處裡方式將兩個分支的測試檔案同一行寫成不一樣(ex:  123 vs 142)。
	- git merge 問題處裡工具: winmerge。