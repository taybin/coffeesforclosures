---
title: goodbye Carbon and good riddence
date: 2008-07-07T21:59:31+00:00
author: Taybin Rutkin
---

From the documentation for GetProcessInformation()

> You need to specify values for the processInfoLength, processName, and processAppSpec fields of the process information structure. Specify the length of the process information structure in the processInfoLength field. If you do not want information returned in the processName and processAppSpec fields, specify NULL for these fields. Otherwise, allocate at least 32 bytes of storage for the string pointed to by the processName field and, in the processAppSpec field, specify a pointer to an FSSpec structure.

[no joke](http://developer.apple.com/documentation/Carbon/Reference/Process_Manager/Reference/reference.html#//apple_ref/c/func/GetProcessInformation)

Rollover Carbon, rock on OOP.
