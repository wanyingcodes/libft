# 📚 libft

## 📌 Overview

`libft` is a custom C library that reimplements a subset of the standard C library (`libc`) and extends it with additional utility functions and linked list operations.  

The goal of this project is to build a **reusable, low-level toolkit in C**, reinforcing memory management, pointer handling, and clean modular design.  

This library becomes a foundation for later projects in School 42.  

## ⚙️ Build

### 📦 Compile the library

```bash
make
```

This will generate:  

```text
libft.a
```

### 🧹 Clean objects

```bash
make clean
```

### 🧼 Full clean

```bash
make fclean
```

### 🔁 Rebuild

```bash
make re
```

## 🧠 Implementation Overview

The library is structured into three main parts:  

## 1️⃣ Libc Reimplementation

Recreation of standard C functions with `ft_` prefix.  

### Includes:

* Character checks: `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`  
* String handling: `ft_strlen`, `ft_strlcpy`, `ft_strlcat`, `ft_strdup`  
* Memory operations: `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`  
* Case conversion: `ft_toupper`, `ft_tolower`  
* Search & compare: `ft_strchr`, `ft_strrchr`, `ft_strncmp`, `ft_strnstr`  
* Conversion: `ft_atoi`  
* Allocation: `ft_calloc`  

👉 Focus: correctness, edge cases, and strict libc behavior replication.  

## 2️⃣ String Utility Functions

Higher-level string operations built on top of libc functions.  

* `ft_substr` → extract substring  
* `ft_strjoin` → concatenate strings  
* `ft_strtrim` → trim characters from ends  
* `ft_split` → split string into array  
* `ft_itoa` → integer to string conversion  
* `ft_strmapi` → map function over string  
* `ft_striteri` → in-place string iteration  

👉 Focus: dynamic memory handling + safe string construction.  

## 3️⃣ File Descriptor Output Utilities

Simple output helpers using `write()`:  

* `ft_putchar_fd`  
* `ft_putstr_fd`  
* `ft_putendl_fd`  
* `ft_putnbr_fd`  

👉 Focus: low-level output abstraction without stdio.  

## 4️⃣ Linked List Toolkit

A generic singly linked list implementation:  

```c
typedef struct s_list
{
    void            *content;
    struct s_list   *next;
} t_list;
```

### Core operations:

* `ft_lstnew` → create node  
* `ft_lstadd_front` / `ft_lstadd_back` → insert nodes  
* `ft_lstsize` → count nodes  
* `ft_lstlast` → get last node  
* `ft_lstdelone` → delete single node  
* `ft_lstclear` → clear full list  
* `ft_lstiter` → apply function to nodes  
* `ft_lstmap` → transform list into new list  

👉 Focus: generic data handling + safe memory cleanup patterns.  

## 🧠 Design Principles

* ❌ No global variables  
* ❌ No external libc usage (beyond allowed system calls)  
* ✅ Strict memory safety (no leaks, no invalid frees)  
* ✅ Minimal and reusable implementations  
* ✅ Each function is independent and modular  
* ✅ Edge cases handled explicitly (NULL, empty strings, overflow behavior)  

## 🧪 Testing

You can test functions individually using a `main.c`:  

```bash
gcc -Wall -Wextra -Werror main.c libft.a
./a.out
```

For full validation:  

* Compare behavior with standard libc functions  
* Use edge-case inputs (NULL, empty strings, large numbers)  
* Stress-test memory allocation functions (`calloc`, `split`, `lstmap`)  

## 📌 Summary

`libft` is not just a collection of functions — it is a **reconstruction of core C functionality**, built with strict constraints and manual memory control.  

It serves as a **foundation library for all future C projects**, emphasizing correctness, safety, and modular design.  

## 📬 Contact

GitHub: [https://github.com/wanyingcodes](https://github.com/wanyingcodes)
