指令筆記
===========

## find
* find &lt;PATH&gt; -type f -name &lt;FILENAME&gt;
	* 例如
		* find /home/website/html/ -type f -name "*.php"
		* find /home/website/html/ -type f -name "*.php" -exec ls {} +
	* 嵌入指令的例子
		* tar cvzf tarball.tar.gz $(find /home/website/html/ -type f -name "*.php" -exec ls {} +)




