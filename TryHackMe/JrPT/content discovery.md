# content discovery

the process of finding content that wasn't meant to be accessible

robots.txt = often found lists of sensitive directories, tells search engine how to interact with the site

sitemap.xml = tells search engine what pages should be listed

HTTP header = reveals useful technical details,  curl http://10.114.148.198 -v

Google dorking = lets you filter results to find sensitive content

site	      |site:tryhackme.com	  |Returns results only from the specified domain

inurl	      |inurl:admin	        |Returns results with the specified word in the URL

filetype  	|filetype:pdf	        |Returns results of a specific file type

intitle   	|intitle:admin      	|Returns results with the specified word in the page title

intext  	  |intext:password	    |Returns results containing the specified word in the body

cache   	  |cache:tryhackme.com	|Shows Google's cached version of the page

