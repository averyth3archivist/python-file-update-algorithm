# Python Algorithm for File Updates
## Portfolio Project from Google Cybersecurity Professional Certificate

### Project description
As a fictitious healthcare company's security professional, I regularly updated a file listing employees authorized to access restricted content based on their handling of patient records. Access was restricted by IP address, with an allow list for permitted IPs and a remove list for exclusions. My task was to develop a Python algorithm to remove IPs listed on the remove list from the ```"allow_list.txt"```.


### Open the file that contains the allow list
I initially opened the ```"allow_list.txt"``` file, assigning it's file name as a string to the ```import_file``` variable.

![alt text][figure1]

[figure1]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_1.png "Figure 1"

I then used a ```with``` statement to open the file.

![alt text][figure2]

[figure2]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_2.png "Figure 2"

I used the "with" statement with the ".open()" function in read mode to access the allow list file for reading purposes. This allows me to retrieve the IP addresses stored in the file. The "with" keyword ensures proper resource management by automatically closing the file after exiting the statement block. The code snippet has two parameters: the first specifies the file to import, and the second indicates the desired file operation - in this case, "r" denotes reading mode. 

### Read the file contents
I used the ```.read()``` method to convert the file contents into a string to be read.

![alt text][figure3]

[figure3]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_3.png "Figure 3"

### Convert the string into a list
![alt text][figure4]

[figure4]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_4.png "Figure 4"

To transform individual IP addresses into a list format for removal from the allow list, I utilized the ```.split()``` method to convert the ```ip_addresses``` string. This method, when appended to a string variable, splits its contents into a list, simplifying subsequent IP removal operations. By default, ```.split()``` divides text by whitespace into list elements. In this case, it transformed the ```ip_addresses``` string, containing whitespace-separated IP addresses, into a list. This list was then reassigned to the ```ip_addresses``` variable.


### Iterate through the remove list
Iterating through IP addresses listed in the ```remove_list``` was achieved through a ```for ```loop. This loop iterated over the sequence of IP addresses stored in the ```ip_addresses``` list, applying specific operations to each element.

![alt text][figure5]

[figure5]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_5.png "Figure 5"


### Remove IP addresses that are on the remove list
Utilizing a conditional statement within this loop, I verified if each IP address from the ```remove_list``` existed in the ip_addresses list. Upon confirmation, the ```.remove()``` method was applied to delete the IP address from ip_addresses.

![alt text][figure6]

[figure6]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_6.png "Figure 6"

### Update the file with the revised list of IP addresses 
To finalize the algorithm, updating the allow list file with the revised list of IP addresses was necessary. Firstly, the list had to be converted back into a string format, accomplished using the ```.join()``` method, which concatenates elements of an iterable into a single string with specified separators. 

![alt text][figure7]

[figure7]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_7.png "Figure 7"

Employing ```.join()``` on the ```ip_addresses``` list allowed me to create a string with each IP address on a separate line (using the string ```"\n"``` as a separator), ideal for updating the ```"allow_list.txt"``` file. 

![alt text][figure8]

[figure8]: https://github.com/averyth3archivist/python-file-update-algorithm/blob/47198742ac3931056d845a332c9fef40cb03c48f/python_fileupdate_8.png "Figure 8"

The ```with``` statement and ```.write()``` method facilitated this update, with the ```"w"``` argument indicating the intention to overwrite the file contents. By appending ```.write()``` to the file object within the with statement, I replaced the file's previous content with the updated ```ip_addresses``` data, thereby ensuring restricted content accessibility only to approved IP addresses.

### Summary
I developed an algorithm to eliminate IP addresses listed in a ```remove_list``` variable from the ```"allow_list.txt"``` file, which contains approved IP addresses. The process involved opening the file, converting its contents into a readable string, and subsequently transforming this string into a list stored as the variable ```ip_addresses```. Next, I iterated through the IP addresses in ```remove_list```, checking if each element existed in the ```ip_addresses``` list. Upon confirmation, I utilized the ```.remove()``` method to delete the element from ```ip_addresses```. Following this, I used the ```.join()``` method to convert ```ip_addresses``` back into a string format, allowing me to overwrite the contents of the ```"allow_list.txt"``` file with the updated list of IP addresses.
