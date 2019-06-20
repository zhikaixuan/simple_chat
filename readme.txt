    多线程编译使用-D_REENTRANT,这个宏定义会让libc和一些其他库，自动选择线程安全的函数实现（很多函数有线程安全和不安全的2种实现版本），
    运行（先生成可执行文件）：gcc chat_server.c -o cserv -pthread
                             （或）gcc chat_server.c -D_REENTRANT -o cserv -pthread
                             gcc chat_client.c -o cclnt -pthread
                             （或）gcc chat_client.c -D_REENTRANT -o cclnt -pthread


在一个终端运行：./cserv 9190
新建一个终端为聊天对象Mike：./cclnt 127.0.0.1 9190 Mike
新建一个终端为聊天对象Jim：./cclnt 127.0.0.1 9190 Jim

然后就可以进行对话了
