指令筆記
===========

## find
* find &lt;PATH&gt; -type f -name &lt;FILENAME&gt;
	* 例如
		* find /home/website/html/ -type f -name "*.php"
		* find /home/website/html/ -type f -name "*.php" -exec ls {} +
		* find /home/website/html/ -type f \\( -iname "\*.php" -o -iname "\*.xml" \\) -exec ls {} +
		
			說明: 不分大小寫找尋副檔名為php或xml的檔案
			
		* find /home/website/html/ -type f -iname "\*.php" -exec ls {} + -o -iname "\*.xml" -exec ls {} +
			
			說明: 效果與上個例子相似，但實際上卻不相同
			
		* find /home/website/html/ -type f \\( -iname "\*.php" -o -iname "\*.xml" -o -iname "\*.js" -o -iname "\*.html" \\) -exec ls {} +
		* find /home/website/html/ -type f ! \\( -iname "\*.txt" -o -iname "\*.zip" -o -iname "\*.apk" -o -iname 95 -o -iname 177 -o -iname "\*.7z" \\) -exec ls {} + | sed 's/\\ /\\\\ /g'

			說明: 找出排除項目類型的檔案並列出，如果列出的檔案名稱有空白字元，將其加入反斜線符號(\)
		
	* 嵌入指令的例子
		* tar cvzf tarball.tar.gz $(find /home/website/html/ -type f -name "*.php" -exec ls {} +)

## grep
* grep --color=auto "[[:digit:]]*\.[[:digit:]]*\.[[:digit:]]*\.[[:digit:]]" Hisi_log/Hisi_log/android/android_2.log

* grep --color=auto -E "([0-9]{1,3}[\.]){3}[0-9]{1,3}" Hisi_log/Hisi_log/android/android_2.log

* grep --color=auto -E -o "([0-9]{1,3}[\.]){3}[0-9]{1,3}" Hisi_log/Hisi_log/android/android_2.log

* grep --color=auto -E "112.4.131.214.*zip" 2019112115-svc.ptsharp.gitv.tv








