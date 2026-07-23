---
title: 用C++做的一个聊天机器人程序
date: 2023-08-02 14:21:53
tags: C++, chatbot
categories: create
---
> Introduction
平时你们有没有用过Chat GPT呢？Chat GPT是一个由Open AI开发的一款聊天软件，是一个网页版的聊天软件，所以一般的电脑安装Chat GPT后一运行就是先等待的一会才有东西显示，因为这个软件是由软件进行的一段程序进行访问Chat GPT的网址，但是在国内会无法访问（中国大陆），但是在国内也有像公益版的Chat GPT，链接在文章末尾提供。

注：本人看了一下Chat GPT的源代码，发现Chat GPT原版复刻需要大量的算法资源，这种算法简直是天数级别。（资源文件文件已从官方获取，但代码天书，🎶我不想说~~🎶

## 一个聊天机器人的条件

首先一个聊天机器人需要让它知道你在说什么，以上已说明，所以我用简单的比较法进行了编程，所以我使用了一个函数：userMessage用来输入，对于这个代码我们首先要将使用者输入的内容进行大小写转换，以能够更正确的让机器进行比较。

```cpp
// 函数用于将用户输入的字符串转换为小写
std::string toLowerCase(std::string str) {
    for (int i = 0; i < str.length(); i++) {
        if (str[i] >= 'A' && str[i] <= 'Z') {
            str[i] = str[i] - 'A' + 'a';
        }
    }
    return str;
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

这个代码是用于将输入的文字转换为小写的函数定义，中文转换为小写之后能和代码的格式ANSI进行比较，从而表现更准确的内容，以后使用就能用toLowerCase(输入内容)让输入的字符格式转换，比如这样：

```cpp
input = toLowerCase(input);
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

大小写转换好了之后，就可以开始定义用来输入的函数以及用函数进行比较，我用了这个函数：userMessage，用来把用户输入的内容进行比较。

```cpp
//用户消息处理函数
void userMessage(const std::string& message)/*定义userMessage*/{
    std::string lowerCaseMessage = toLowerCase(message);
    
    if (lowerCaseMessage == "hello" || lowerCaseMessage == "hi") {
        std::cout << "Hello! How can I assist you?" << std::endl;//如果收到的消息是"hello"或"hi"，则输出"Hello! How can I assist you?"。
    } else if (lowerCaseMessage == "how are you?") {
        std::cout << "I'm fine, thank you! How about you?" << std::endl;//如果收到的消息是"how are you?"，则输出"I'm fine, thank you! How about you?"。
    } else if (lowerCaseMessage == "what is your name?" || lowercaseMessage == "what's your name?") {
        std::cout << "My name is ChatBot." << std::endl;//如果收到的消息是"what is your name?"或者是"what's your name?"，则输出"My name is ChatBot."。
    } else if (lowerCaseMessage == "bye" || lowerCaseMessage == "goodbye") {
        std::cout << "Goodbye! Have a nice day!" << std::endl;//如果收到的消息是"how are you?"，则打印"I'm fine, thank you! How about you?"。
    } else {
        std::cout << "Sorry, I didn't understand your message." << std::endl;//如果上述信息不匹配，那么输出"Sorry, I didn't understand your message."。
    }
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

这个函数定义好了之后，我们半个聊天机器人就完成了，我们可以再设一个判断以及简单的输出输入外观，这里我就不做解释了，因为我都是以简单的C++完成的，即使是小白也看得懂一半差不多。

```cpp
int main() {
    std::string message;
    std::cout << "Welcome to ChatBot! Start messaging." << std::endl;

    while (true) {
        std::cout << "You: ";
        std::getline(std::cin, message);

        if (message == "exit") {
            break;
        }

        userMessage(message);
    }

    return 0;
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

之后再上完整代码：

```cpp
#include <iostream>
#include <string>
#include <algorithm>
std::string toLowerCase(const std::string& str) {
    std::string lowerCaseStr = str;
    std::transform(lowerCaseStr.begin(), lowerCaseStr.end(), lowerCaseStr.begin(), ::tolower);
    return lowerCaseStr;
}
void userMessage(const std::string& message) {
    std::string lowerCaseMessage = toLowerCase(message);
    if (lowerCaseMessage == "hello" || lowerCaseMessage == "hi") {
        std::cout << "Hello! How can I assist you?" << std::endl;
    } else if (lowerCaseMessage == "how are you?") {
        std::cout << "I'm fine, thank you! How about you?" << std::endl;
    } else if (lowerCaseMessage == "what is your name?") {
        std::cout << "My name is ChatBot." << std::endl;
    } else if (lowerCaseMessage == "bye" || lowerCaseMessage == "goodbye") {
        std::cout << "Goodbye! Have a nice day!" << std::endl;
    } else {
        std::cout << "Sorry, I didn't understand your message." << std::endl;
    }
}

int main() {
    std::string message;
    std::cout << "Welcome to ChatBot! Start messaging." << std::endl;
    while (true) {
        std::cout << "You: ";
        std::getline(std::cin, message);
        if (message == "exit") {
            break;
        }
        userMessage(message);
    }
    return 0;
}
```

![点击并拖拽以移动](data:image/gif;base64,R0lGODlhAQABAPABAP///wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==)

> Chat GPT:[ChatGPT (openai.com)](https://openai.com/chatgpt)
>
> 公益版：[Ai Chat公益版 (00chatgpt.com)](https://ai1.00chatgpt.com/)