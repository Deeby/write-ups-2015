# nullcon HackIM 2015: Forensics 500

**Category:** Forensics
**Points:** 500
**Author:**
**Description:**

> This image contains a pagefile. Can you tell the size of it (in bytes)? 
>
> Password to open archive:Synergy@123
>
> Flag format: flag{flag}
>
>	Image.rar

## Write-up

The image file is a Windows memory dump generated by virtual machine manager.

Get strings in the image and search for page file size:

~~~bash
$ strings Image > str
$ grep -i pagefilesize str
PagefileSize: 0x7ff7e000
$ python -c 'print 0x7ff7e000'
2146951168
~~~

The flag is `flag{2146951168}`.


## Other write-ups and resources

* <https://zairon.wordpress.com/2015/01/19/nullcon-hackim-2015-forensics-500-writeup/>
* <http://blog.tinduong.pw/nullcon-hackim-2014-write-ups/>