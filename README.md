# Linux

file 1a shopping list and file 1b shopping list module 25

[centos@vbox ~]$ touch shopping_list.txt
[centos@vbox ~]$ sudo yum install nano -y
Last metadata expiration check: 3:15:20 ago on Tue 21 Jan 2025 11:55:00 GMT.
Package nano-5.6.1-7.el9.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!
[centos@vbox ~]$ sudo yum install nano -y
Last metadata expiration check: 3:15:20 ago on Tue 21 Jan 2025 11:55:00 GMT.
Package nano-5.6.1-7.el9.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!
[centos@vbox ~]$ nano shopping_list.txt
[centos@vbox ~]$ [centos@vbox ~]$ nano shopping_list.txt
[centos@vbox ~]$ [centos@vbox ~]$ cat shopping_list.txt | grep "of"
Box of cereal
Loaf of bread
Carton of eggs
[centos@vbox ~]$ cat shopping_list.txt | grep -i "[Dd]og"
12 hot dog buns
Dog food
[centos@vbox ~]$ cat shopping_list.txt | grep "[0-9]"
12 hot dog buns
12 sausages
[centos@vbox ~]$ cat shopping_list.txt | grep "^[A-Z][^t]*[s]$"
Bananas
Grapes
Pears
[centos@vbox ~]$ cat shopping_list.txt | grep "^[A-Z][^t]*[s]$"
Bananas
Grapes
Pears
[centos@vbox ~]$ rm shopping_list.txt
[centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ [centos@vbox ~]$ grep "[DdLl]is[kt]" sample_text.txt
[centos@vbox ~]$ grep "[DdLl]is[kt]" sample_text.txt
[centos@vbox ~]$ grep "th[a-z]" sample_text.txt
[centos@vbox ~]$ grep "th[o-u]" sample_text.txt
[centos@vbox ~]$ grep "th[^o-u]" sample_text.txt
[centos@vbox ~]$ grep "^L" sample_text.txt
[centos@vbox ~]$ grep "files.$" sample_text.txt
[centos@vbox ~]$ grep "files.$" sample_text.txt
[centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ [centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ grep "[DdLl]is[kt]" sample_text.txt
[centos@vbox ~]$ grep "th[a-z]" sample_text.txt
[centos@vbox ~]$ grep "th[o-u]" sample_text.txt
[centos@vbox ~]$ grep "th[^o-u]" sample_text.txt
[centos@vbox ~]$ grep "^L" sample_text.txt
Loaf of bread
[centos@vbox ~]$ grep "files.$" sample_text.txt
[centos@vbox ~]$ grep "files\." sample_text.txt
[centos@vbox ~]$ grep "[Ll]inux." sample_text.txt
[centos@vbox ~]$ grep "[Ll]inux.$" sample_text.txt
[centos@vbox ~]$ grep "L.*" sample_text.txt
Loaf of bread
[centos@vbox ~]$ grep "h.*x" sample_text.txt
[centos@vbox ~]$ grep "h.*x.$" sample_text.txt
[centos@vbox ~]$ grep "h.*x.$" sample_text.txt
[centos@vbox ~]$ !! > grep_output.txt
grep "h.*x.$" sample_text.txt > grep_output.txt
[centos@vbox ~]$ cat grep_output.txt
[centos@vbox ~]$ cat grep_output.txt
[centos@vbox ~]$ ls | grep "\.txt"
grep_output.txt
sample_text.txt
test.txt
[centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ ls | grep "\.txt"
grep_output.txt
sample_text.txt
test.txt
[centos@vbox ~]$ !! > list_of_text_files
ls | grep "\.txt" > list_of_text_files
[centos@vbox ~]$ cat list_of_text_files
grep_output.txt
sample_text.txt
test.txt
[centos@vbox ~]$ /Linux
-bash: /Linux: No such file or directory
[centos@vbox ~]$ n
-bash: n: command not found
[centos@vbox ~]$ N
-bash: N: command not found
[centos@vbox ~]$ touch shopping_list.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ rm shopping_list.txt
[centos@vbox ~]$ touch sample_text.txt
[centos@vbox ~]$ nano sample_text.txt
[centos@vbox ~]$ grep "[DdLl]is[kt]" sample_text.txt
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
IMAGE:List of Large Text Files
[centos@vbox ~]$ grep "th[a-z]" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Given all of this, some text files can get pretty big. And often we’re not talking about dozens of MB, but possibly hundreds, or even a few gigabytes in size in rare occasions. And all of it can be text! In fact, something as innocuous as a log file can continue to grow if left unchecked. Let’s say you have a file recording every visit to your website, along with the date, IP, user-agent, etc. For even a medium-sized website, that file can grow pretty large if not dealt with.
In this article, we’ll look at how to view these large files without slowing down your system. Sometimes you might even need to edit these large files, which is far more difficult to deal with when the files are of this magnitude. Luckily, it’s quite unheard of for a configuration file to be large enough to make it problematic to edit! Let’s begin.
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
This will give you an output like this. Note that it may take a while for the results to appear onscreen:
As you can see, most of these are binary files or databases that you can’t open directly. But often you’ll find mail logs that keep a record of even spam attempts to access your server. And if your IP address is hit often, that mail spool will just keep getting bigger and bigger, reaching hundreds of MB in a matter of a few months.
Trying to Open Large Files the Traditional Way
For this example, we’re going to create an example text file and bloat its size using the “truncate” command like this:
Where “testfile” is the sample file. This command will set its size to 20MB and fill the extra space with null characters. We can get the size of all the files in the current directory in MB using this command:
Here’s the output:
IMAGE: Creating a 20MB Test File in the Directory
We will use the traditional text editor called “vi” to open the file and close it as soon as it’s loaded. To know how long the entire operation lasted, we use the “time” command, like this:
And when we exit vi after “testfile” has displayed its contents, it gives us the duration of the entire operation like this:IMAGE: Opening and Closing the File Using vi
So in this case, it takes us almost 6 seconds for a file that’s just 20 MB! That’s an absurd amount of time for a powerful processor. What happens when we increase the size to 40 MB?
It now takes us 23 seconds! So the time increases non-linearly. When the file is larger, it takes exponentially longer to open.
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
Where [filename] is the name of the large file you want open. You can see in the screenshot below that it opens a huge file in less than a second:
Most of that time is used by having to manually quit the program. So it’s pretty much instantaneous! We can navigate to the next “block” in the file by pressing “f” and we can go back by pressing “b”. We can also use “j” and “k”, or the arrow keys, to navigate between lines.
So the next time you see a file of hundreds of MB and need to view it, use “less” instead of “vi” or “cat”. Your system resources will thank you for it, and you’ll save time as well!
[centos@vbox ~]$ grep "th[o-u]" sample_text.txt
In this article, we’ll look at how to view these large files without slowing down your system. Sometimes you might even need to edit these large files, which is far more difficult to deal with when the files are of this magnitude. Luckily, it’s quite unheard of for a configuration file to be large enough to make it problematic to edit! Let’s begin.
As you can see, most of these are binary files or databases that you can’t open directly. But often you’ll find mail logs that keep a record of even spam attempts to access your server. And if your IP address is hit often, that mail spool will just keep getting bigger and bigger, reaching hundreds of MB in a matter of a few months.
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
[centos@vbox ~]$ grep "th[^o-u]" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Given all of this, some text files can get pretty big. And often we’re not talking about dozens of MB, but possibly hundreds, or even a few gigabytes in size in rare occasions. And all of it can be text! In fact, something as innocuous as a log file can continue to grow if left unchecked. Let’s say you have a file recording every visit to your website, along with the date, IP, user-agent, etc. For even a medium-sized website, that file can grow pretty large if not dealt with.
In this article, we’ll look at how to view these large files without slowing down your system. Sometimes you might even need to edit these large files, which is far more difficult to deal with when the files are of this magnitude. Luckily, it’s quite unheard of for a configuration file to be large enough to make it problematic to edit! Let’s begin.
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
This will give you an output like this. Note that it may take a while for the results to appear onscreen:
As you can see, most of these are binary files or databases that you can’t open directly. But often you’ll find mail logs that keep a record of even spam attempts to access your server. And if your IP address is hit often, that mail spool will just keep getting bigger and bigger, reaching hundreds of MB in a matter of a few months.
Trying to Open Large Files the Traditional Way
For this example, we’re going to create an example text file and bloat its size using the “truncate” command like this:
Where “testfile” is the sample file. This command will set its size to 20MB and fill the extra space with null characters. We can get the size of all the files in the current directory in MB using this command:
Here’s the output:
IMAGE: Creating a 20MB Test File in the Directory
We will use the traditional text editor called “vi” to open the file and close it as soon as it’s loaded. To know how long the entire operation lasted, we use the “time” command, like this:
And when we exit vi after “testfile” has displayed its contents, it gives us the duration of the entire operation like this:IMAGE: Opening and Closing the File Using vi
So in this case, it takes us almost 6 seconds for a file that’s just 20 MB! That’s an absurd amount of time for a powerful processor. What happens when we increase the size to 40 MB?
It now takes us 23 seconds! So the time increases non-linearly. When the file is larger, it takes exponentially longer to open.
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
Where [filename] is the name of the large file you want open. You can see in the screenshot below that it opens a huge file in less than a second:
Most of that time is used by having to manually quit the program. So it’s pretty much instantaneous! We can navigate to the next “block” in the file by pressing “f” and we can go back by pressing “b”. We can also use “j” and “k”, or the arrow keys, to navigate between lines.
So the next time you see a file of hundreds of MB and need to view it, use “less” instead of “vi” or “cat”. Your system resources will thank you for it, and you’ll save time as well!
[centos@vbox ~]$ grep "^L" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
[centos@vbox ~]$ grep "^L" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
[centos@vbox ~]$ grep "files.$" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
[centos@vbox ~]$ grep "files.$" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
[centos@vbox ~]$ grep "files\." sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
[centos@vbox ~]$ grep "[Ll]inux." sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Listing the Largest Files on your Linux System
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ grep "[Ll]inux.$" sample_text.txt
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ grep "L.*" sample_text.txt
How to Efficiently Manage Large Text Files in Linux
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Given all of this, some text files can get pretty big. And often we’re not talking about dozens of MB, but possibly hundreds, or even a few gigabytes in size in rare occasions. And all of it can be text! In fact, something as innocuous as a log file can continue to grow if left unchecked. Let’s say you have a file recording every visit to your website, along with the date, IP, user-agent, etc. For even a medium-sized website, that file can grow pretty large if not dealt with.
In this article, we’ll look at how to view these large files without slowing down your system. Sometimes you might even need to edit these large files, which is far more difficult to deal with when the files are of this magnitude. Luckily, it’s quite unheard of for a configuration file to be large enough to make it problematic to edit! Let’s begin.
Listing the Largest Files on your Linux System
Let’s say you need to clean out some space on your hard drive and want a list of the biggest culprits eating up your disk space. To get a list of the top 10 largest files, use this command:
IMAGE:List of Large Text Files
Trying to Open Large Files the Traditional Way
IMAGE: The Execution Time Increases Non-Linearly
Using “Less” is More Efficient
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
IMAGE:The Less Command Opens Files Almost Instantaneously
[centos@vbox ~]$ grep "h.*x" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Given all of this, some text files can get pretty big. And often we’re not talking about dozens of MB, but possibly hundreds, or even a few gigabytes in size in rare occasions. And all of it can be text! In fact, something as innocuous as a log file can continue to grow if left unchecked. Let’s say you have a file recording every visit to your website, along with the date, IP, user-agent, etc. For even a medium-sized website, that file can grow pretty large if not dealt with.
Listing the Largest Files on your Linux System
For this example, we’re going to create an example text file and bloat its size using the “truncate” command like this:
Where “testfile” is the sample file. This command will set its size to 20MB and fill the extra space with null characters. We can get the size of all the files in the current directory in MB using this command:
We will use the traditional text editor called “vi” to open the file and close it as soon as it’s loaded. To know how long the entire operation lasted, we use the “time” command, like this:
And when we exit vi after “testfile” has displayed its contents, it gives us the duration of the entire operation like this:IMAGE: The Execution Time Increases Non-Linearly
It now takes us 23 seconds! So the time increases non-linearly. When the file is larger, it takes exponentially longer to open.
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
Most of that time is used by having to manually quit the program. So it’s pretty much instantaneous! We can navigate to the next “block” in the file by pressing “f” and we can go back by pressing “b”. We can also use “j” and “k”, or the arrow keys, to navigate between lines.
So the next time you see a file of hundreds of MB and need to view it, use “less” instead of “vi” or “cat”. Your system resources will thank you for it, and you’ll save time as well!
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ grep "h.*x" sample_text.txt
Linux is an operating system of text files. Unlike Windows, the Linux philosophy and core concept is that “everything is a file”. Sure, there are databases and binary structures, but nothing like Windows’ “Registry” exists. Even devices, partitions, and sockets are represented either by real or virtual files.
Given all of this, some text files can get pretty big. And often we’re not talking about dozens of MB, but possibly hundreds, or even a few gigabytes in size in rare occasions. And all of it can be text! In fact, something as innocuous as a log file can continue to grow if left unchecked. Let’s say you have a file recording every visit to your website, along with the date, IP, user-agent, etc. For even a medium-sized website, that file can grow pretty large if not dealt with.
Listing the Largest Files on your Linux System
For this example, we’re going to create an example text file and bloat its size using the “truncate” command like this:
Where “testfile” is the sample file. This command will set its size to 20MB and fill the extra space with null characters. We can get the size of all the files in the current directory in MB using this command:
We will use the traditional text editor called “vi” to open the file and close it as soon as it’s loaded. To know how long the entire operation lasted, we use the “time” command, like this:
And when we exit vi after “testfile” has displayed its contents, it gives us the duration of the entire operation like this:IMAGE: The Execution Time Increases Non-Linearly
It now takes us 23 seconds! So the time increases non-linearly. When the file is larger, it takes exponentially longer to open.
Luckily for us, we have a command called “less” which reads the contents of the file one block at a time, and thus spares us the problem of loading it all at once. The syntax is simple:
Most of that time is used by having to manually quit the program. So it’s pretty much instantaneous! We can navigate to the next “block” in the file by pressing “f” and we can go back by pressing “b”. We can also use “j” and “k”, or the arrow keys, to navigate between lines.
So the next time you see a file of hundreds of MB and need to view it, use “less” instead of “vi” or “cat”. Your system resources will thank you for it, and you’ll save time as well!
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ grep "h.*x.$" sample_text.txt
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ !! > grep_output.txt
grep "h.*x.$" sample_text.txt > grep_output.txt
[centos@vbox ~]$ cat grep_output.txt
font: https://linuxhostsupport.com/blog/how-to-efficiently-manage-large-text-files-in-linux/
[centos@vbox ~]$ ls | grep "\.txt"
grep_output.txt
sample_text.txt
test.txt
[centos@vbox ~]$ !! > list_of_text_files
ls | grep "\.txt" > list_of_text_files
[centos@vbox ~]$ !! > list_of_text_files
ls | grep "\.txt" > list_of_text_files > list_of_text_files
[centos@vbox ~]$ cat list_of_text_files
grep_output.txt
sample_text.txt
test.txt
[centos@vbox ~]$ /linux
-bash: /linux: No such file or directory
[centos@vbox ~]$
