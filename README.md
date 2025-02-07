# Python
<img width="857" alt="Screenshot 2025-02-06 at 9 19 02 PM" src="https://github.com/user-attachments/assets/40f53e83-530b-42c2-adfa-1c63fa473251" />


# **Update a File Through a Python Algorithm**  

---  

## **Project Description**  

At my organization, access to restricted content is controlled with an **allow list** of IP addresses. The `"allow_list.txt"` file identifies these IP addresses. A separate **remove list** contains IP addresses that should **no longer** have access.  

I created a **Python algorithm** to **automate updating** the `"allow_list.txt"` file by removing the IP addresses that should no longer have access.  

---  

## **Steps in the Algorithm**  

### **1. Open the Allow List File**  
To begin, I opened the `"allow_list.txt"` file by assigning the file name to a variable and using the `with` statement:  

```python
import_file = "allow_list.txt"

with open(import_file, "r") as file:
    ip_addresses = file.read()
```  

- The **`with` statement** ensures that the file is properly closed after reading.  
- The **`"r"` mode** (read mode) allows access to **read the file's contents**.  

---  

### **2. Read the File Contents**  
To store the **IP addresses**, I used the `.read()` method:  

```python
ip_addresses = file.read()
```  

- The `.read()` method **converts** the file's content into a **string format**.  
- This enables easier **data manipulation** in later steps.  

---  

### **3. Convert the String into a List**  
To efficiently remove **individual** IP addresses, I converted the string into a **list**:  

```python
ip_addresses = ip_addresses.split()
```  

- The `.split()` method **splits** the string into **list elements**, making each IP address an item in the list.  
- This **facilitates removal** of specific IP addresses.  

---  

### **4. Iterate Through the Remove List**  
I used a `for` loop to **iterate** through the list of IP addresses that need to be removed:  

```python
remove_list = ["192.168.1.1", "10.0.0.2"]  # Example remove list

for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
```  

- The `for` loop checks if each **IP address** in `remove_list` exists in `ip_addresses`.  
- If an **IP address is found**, it is **removed** using `.remove()`.  
- This ensures that only **approved** IPs remain.  

---  

### **5. Update the File with the Revised List**  
After modifying the list, I **converted it back** into a string and updated the file:  

```python
updated_ip_addresses = "
".join(ip_addresses)

with open("allow_list.txt", "w") as file:
    file.write(updated_ip_addresses)
```  

- The `.join("
")` method ensures that **each IP address is placed on a new line**.  
- The `open("allow_list.txt", "w")` statement opens the file in **write mode** (`"w"`) to overwrite the existing content.  

---  

## **Summary**  

- I created an algorithm to **automatically update** an allow list of IP addresses.  
- The script **opens and reads** `"allow_list.txt"`, then **removes** unwanted IPs.  
- The **filtered IP list** is written back to the file.  
- This **automates** the process of **managing** access permissions efficiently.  

