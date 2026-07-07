This page explains the three main categories of **open-source software licenses** and how they affect the way software can be used, modified, and redistributed.
# Permissive Licenses
Permissive licenses place **very few restrictions** on users.

- You can use, modify, and redistribute the software.
- You can incorporate the code into **proprietary (closed-source) products**.
- You are generally not required to release your modifications to the public.
- Future versions of the software might become proprietary.

### Examples: 
**MIT License, BSD License, Apache License**

### Example scenario:
- A company takes an MIT-licensed library, modifies it, and includes it in a commercial product without releasing the modified source code. This is generally allowed.

# Weak Copyleft Licenses
Weak copyleft licenses try to balance open-source requirements with commercial flexibility.


- Modifications to the licensed component **itself typically must remain open source**.
- Other software can link to or use the library without having to adopt the same license.
- Often used for **software libraries**.

### Examples:

- LGPL (Lesser GPL)
- MPL (Mozilla Public License)
- EPL (Eclipse Public License)
- CDDL (Common Development and Distribution License)

### Example scenario:
- **glibc (GNU C Library)** uses a weak copyleft license (LGPL).
  - glibc: standard C runtime library used by most Linux systems including `printf()`, `malloc()`, `free()`
- A proprietary application links to an LGPL library. The application **can remain closed source**, while changes made directly to the LGPL library must be made available under the LGPL.

# Strong Copyleft Licenses
Strong copyleft licenses require derivative works to **remain under the same license**.

- If you modify the software and distribute it, you must release the source code under the same license.
- Software derived from the original work generally inherits the same licensing obligations.
- Designed to ensure that software remains free and open.

### Examples:
- GPL
- GPL v2
- GPL v3
- Affero GPL (AGPL)

### Example scenario:
- If you incorporate GPL-licensed code into your application and distribute the application, you may be required to release the application's source code under the GPL as well.
