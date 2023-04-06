# Memory 

Memory is the place where data and program instructions are stored to execute. There several type of memory are in a computer system, each serving different purpose.
<dl>
  <dt>1 RAM (Random Access Memory) </dt><dd> It is volatile memory that store data and program temporary while the computer running. It memory used for currently running programs.</dd>
  <dt>ROM (Read Only Memory) </dt><dd> These memories are no-volatile memory that store the data and programs which used by the computer during the startup to initialize the hardware and load the operating system. These data and programs in this memory cannot be modified by the user</dd>
  <dt>Cache memory </dt><dd> These are high speed memory that is used to temporarily store the frequently accessed data and instruction.  </dd>
  <dt>Virtual memory </dt><dd> Is a feature that allow the computer to use a portion of hard disk as an extension of main memory</dd>
</dl>

<h3> Memory Allocation </h3>

Memory allocation refers to the process of reserving a portion of computer's memory for a particular purpose.
There are two main type of memory allocation
<ol>
  <li>Static memory allocation : Static memory allocation is the process of allocating memory at compile time. Memory size are fixed at compile time.</li>
  <li>Dynamic memory allocation : Dynamic memory allocation is the process of allocating memory at runtime. Memory size can be changed during runtime.</li>
</ol>

### Have you ever had about 32bit or 64bit  ? 

Bits are nothing but, in computer the data are stored in binary format which is a series of binary digits 0s and 1s. These binary digits also known as bits, are organized into groups of eight, known as bytes.
```
1 byte = 8 bits
1 KB = 1024 bytes
1 GB = 1024 KB
1 TB = 1024 GB
1 PB = 1.024 TB
```

### Memory allocation and memory leaks

memory allocation is a process of reserving and assigning memory space for a program or process to use. 
Memory leaks when programs fails to release the memory that has previously allocated after no longer needed. These program can be solved by using garbage collector in high level language. free(), delete() are used in low level language.