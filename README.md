## **Multithreaded File Compression & Decompression Tool in C++**

### **Overview**
This is a **C++ application** designed to **compress and decompress files** efficiently using **multithreading** to optimize performance. It processes large files by dividing them into smaller chunks and compresses or decompresses these chunks in parallel using multiple threads. The tool utilizes the **zlib** library for compression and decompression.

---

### **Key Features**
✅ **Multithreading for Performance** – Utilizes multiple threads to process chunks of the file in parallel, reducing execution time significantly.  
✅ **Efficient Compression & Decompression** – Uses the **zlib** library for fast and effective data compression.  
✅ **Chunk-Based Processing** – Divides large files into chunks of **256 KB** to handle them efficiently.  
✅ **Scalability** – Works well with large files, taking advantage of modern multi-core CPUs.  
✅ **Simple Command-Line Interface** – Easy-to-use commands for compressing and decompressing files.  

---

### **How It Works**
1. The file is read in **fixed-size chunks (256 KB per chunk)**.
2. Each chunk is **compressed or decompressed** in a separate thread.
3. The **compressed chunks are saved** to an output file (for compression).
4. For decompression, the **chunks are restored** to their original state and written back.

---

### **Usage Instructions**
#### **1. Compilation**
Before using the tool, compile it with the following command:
```sh
g++ -std=c++11 -o file_compressor file_compressor.cpp -lz -pthread
```
Here:
- `-lz` links the **zlib** compression library.
- `-pthread` enables **multithreading** support.

---

#### **2. Compressing a File**
To compress a file, run:
```sh
./file_compressor compress input.txt compressed.dat
```
✅ **Example Output:**
```
Compression completed.
```
The compressed data is saved in `compressed.dat`.

---

#### **3. Decompressing a File**
To decompress a file, run:
```sh
./file_compressor decompress compressed.dat output.txt
```
✅ **Example Output:**
```
Decompression completed.
```
The file `output.txt` should now contain the original content.

---

### **Performance Demonstration**
To compare performance, you can measure execution time using the `time` command.

#### **Compression Timing**
```sh
time ./file_compressor compress largefile.txt largefile_compressed.dat
```
✅ **Example Output:**
```
Compression completed.

real    0m2.356s
user    0m5.321s
sys     0m0.432s
```
This shows the **actual execution time** (`real`), CPU processing time (`user`), and system I/O time (`sys`).

#### **Decompression Timing**
```sh
time ./file_compressor decompress largefile_compressed.dat decompressed_largefile.txt
```
✅ **Example Output:**
```
Decompression completed.

real    0m1.876s
user    0m4.192s
sys     0m0.312s
```

---

### **Why Use Multithreading?**
🔹 Without multithreading, **only one chunk** is processed at a time, which slows down large file compression.  
🔹 With **multiple threads**, several chunks are processed **simultaneously**, utilizing the full potential of multi-core CPUs.  
🔹 This results in **faster execution**, especially for **large files**.

---

### **Possible Enhancements**
🔸 **Adaptive Chunk Sizing** – Dynamically adjust chunk sizes based on available system memory.  
🔸 **Progress Bar or Logging** – Show real-time progress and compression ratios.  
🔸 **Support for More Algorithms** – Extend support for LZ4, BZip2, etc.  
🔸 **GUI Integration** – Add a graphical interface for ease of use.

---

### **Conclusion**
This multithreaded compression tool is a **high-performance, scalable solution** for handling large files efficiently. By leveraging **parallel processing**, it significantly reduces execution time compared to traditional single-threaded methods.

Would you like any modifications or additional features? 🚀
