[toc]

## Abstract

IoT平台通常需要用户给第三方APP以权限，但是由于用户的不熟悉，常常导致恶意程序的过度权限。为了满足IoT环境中的一些诸如跨设备、环境影响、自动操作等的影响，本文作者们设计了以用户为中心的、基于语义的“智能”验证系统SmartAuth。通过分析app的描述、代码和注释，能够帮助用户更好的理解系统需要的功能和系统实际会进行的操作之间的关系。 作者发明了一种利用自然语言处理和程序分析的方法来分析设备环境和活动语义之间的技术。同时实验也证明用户可以通过SmartAuth来更大可能避免过度权限的问题。

Users often grant over-privileged permissions to the third-party IoT aps because of unfamiliar with IoT platform, leading to excessive permissions to malicious apps. The authors designed a user-centric, semantic-based "smart" authentication system SmartAuth by analyzing the description, code and comments of the app to help users better understand the relationship between the functions required by the system and the actual operations the system will perform to avoid the problem of excessive permissions.



## intro

IoT的应用能够控制一些带有潜在的安全威胁的设备（如门锁等）.主要是由于framework下的不充分防护，而这中间最重要的就是在SmartApp验证时的过度权限问题。

- 一些不清晰的验证说明常常有粗糙的粒度和对环境的忽视，即：如一个APP如果被授予了一个设备的某些权限，那么它同时也可能可以实现对这个设备的其他一些功能。
- 同时，APP可能也会尝试去获得一些它根本不需要、甚至是很危险的功能。尽管有些APP有权限询问，但是大量用户常常搞不清楚、或者根本选错。
- 而更糟糕的是，与安卓的权限模型不同，安卓手机上常常会有对一些资源的访问控制，但是这在家庭环境当中也显得==更为复杂==。因此不光向用户解释这些操作很麻烦，同时在给予权限之后对权限使用的监管也是相当的复杂呐。 *所以这就造成了用户理解的功能和实际实现之间的鸿沟。*
- 同时还有使用环境的问题：比如私人信息给医生可以帮助你，但是流落至公众可能就不太好

IoT applications can control some devices with potential security threats (such as door locks, etc.). It is mainly due to insufficient protection under the framework, and the most important thing is the problem of excessive permissions during SmartApp verification.

​		Some unclear verification instructions often have coarse granularity and neglect of the environment, that is, if an APP is granted certain permissions for a device, it may also be able to implement some other functions of the device.
​		At the same time, the APP may also try to obtain some functions that it does not need or even dangerous. Although some apps have permission to inquire, a large number of users often don't know it or choose the wrong one at all.
​		To make matters worse, unlike Android's permission model, Android phones often have access control to some resources, but this also seems to be == more complicated == in the home environment. Therefore, not only is it troublesome to explain these operations to the user, but at the same time, the supervision of the use of the permission after the permission is granted is also quite complicated. *So this creates a gap between the user's understanding of the function and the actual implementation. *
​		At the same time, there is the problem of the use environment: for example, private information to the doctor can help you, but it may not be good if it is left to the public



SmartAuth通过自动收集、分析来自如APP源码、注释和权限请求等的信息来了解IoT 应用的实际功能。由于在应用商店中的应用描述是用户选择这个应用的重要因素之一，他们还采取了NLP来自动提取描述中的功能与实际功能、调用接口进行比较。 NLP还被用在代码注释分析上，用来更快得到开发者的意图。 为了减轻用户负担，SmartAuth还能够根据描述和实际功能之间的差异进行自然语言生成，来告知用户对这些未预料的操作进行处理。

这个工具能被用于检查APP、增强验证制度、为用户提供更好保护上。总体上说他们做的工作如下：

- 使用代码检查和app描述NLP进行用户中心的安全计算
- 设计新的兼容性好的功耗低的家庭自动架构
- 对开发出的SmartAuth进行基于真实情况的评估

SmartAuth understands the actual functions of IoT applications by automatically collecting and analyzing information from APP source code, comments, and permission requests. Since the application description in the application store is one of the important factors for users to choose this application, they also adopted NLP to automatically extract the functions in the description and compare them with the actual functions and call interfaces. NLP is also used in code comment analysis to get developers' intentions faster. In order to reduce the burden on the user, SmartAuth can also generate natural language based on the difference between the description and the actual function to inform the user to deal with these unexpected operations.

This tool can be used to check the APP, enhance the verification system, and provide better protection for users. Generally speaking, the work they do is as follows:

-Use code checking and app description NLP for user center security calculations
-Design a new home automation architecture with good compatibility and low power consumption
-Evaluate the developed SmartAuth based on the real situation