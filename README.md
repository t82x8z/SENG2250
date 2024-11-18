java c
SENG2250 System and Network Security
Assignment 2
This assignment is to be done individually.
Due on Friday, 11 October 2024, 11:59pm, electronically via the “Assignment 2” submission link in Canvas.
Total 100 marks
AimsThe aim of the first part is to establish a secure communication channel using SSL certificates. In the second  part,  you  will  build  a  basic  password  manager  and  enhance  its  security  with  the  RSA algorithm.
Guidelines
You may use any programming language for the tasks below. Additionally, you may use Generative AI tools (e.g., ChatGPT). However, please refer to the “Using Generative AI.pdf” file on Canvas for guidance on how to effectively use these tools and formatting instructions. You must attribute any use of Generative AI, including the prompt used, the tool’s output, your validation/testing/learning process, and your revised results. Directly copying the AI output is not allowed and is considered plagiarism.
Task 1: Securing a Communication Channel with SSL  (45 Marks)
Summary: For this task you will set up SSL certificates with either XCA or OpenSSL, and modify the provided programs to use those certificates.
Problem statement: Jill and Chris have designed a socket-based client server program to covertly communicate with each other, but keep finding that their messages are being leaked. After chatting about this issue with their friend Barry, they learnt of the security technology of SSL and how it may help with maintaining the confidentiality of their communications. So, they have employed you, an up-and-coming cyber security expert, to add SSL functionality to their program, and to set-up the SSL certificates required.
Getting started: On the canvas page you will find the starting code for this task, you have the option of either modifying the Java or Python version. The instructions for the particular set of programs are included in the README.md file in the folder of the respective version. You will want to install either   the XCA (https://hohnstaedt.de/xca/) or OpenSSL (https://www.openssl.org/) programs to create SSL certificates.
Both sets of programs include a server that belongs to Jill, and a Client that belongs to Chris, you can use Wireshark (https://www.wireshark.org/) to see the leak. When creating certificates, have Barry as the CA, and the issuer name match who it belongs to, the other data in the certificates can be anything you want. If you set up the SSL and its usage correctly, the sniffer/interceptor will be unable to recover the messages being sent between Chris and Jill.
Requirements:
•   The SSL certificates are correctly set up, where Barry is the CA and Jill owns the server (15 Marks)
•    Client and server programs use SSL in all socket communications (20 Marks)
•   The interceptor/sniffer program is unable to read communications between Chris and Jill (achieved if the above two points are correct)
Reflective questions:
1.   What other potential security issues are there with this program? Identify and discuss at least three. (6 Marks)
2.   If Barry were to secretly be the leaker, would the program remain secure? Explain why or why not. (4 Marks)
Task 2: A Single Client Password Manager (45 Marks)
For this task, you will develop a basic password manager for a single client. This password manager will be secured with your own implementation of the RSA algorithm. You will have found the correct way to use RSA, i.e. which parts of the messages to encrypt/decrypt, so that the password management server and potential interceptors are never able to see the cleartext passwords. We provide starting files for Java or Python based programs on the Canvas page.
The following sections provide further details for the expected pieces of the program.
RSA
You are to implement and use your own version of the RSA algorithm. On canvas we include a primes.txt file, which you will read p and q from to compute n, ɸ(n), e, and d. To find d, you may use the standard library modular inverse function, i.e. BigInteger.modInverse(), or pow(x, -1, n). For all other places where modular exponentiation is required, you will use your own implementation of the  fast modular exponentiation algorithm.
Password Manager Client<代 写SENG2250 System and Network Security Assignment 2Java
代做程序编程语言br>You will extend the included client.py or Client.java file to have an interface and to correctly handle   passwords. The interface should allow the user to store, retrieve, or end the program in any order at any point. The interface should gracefully handle erroneous inputs and received messages.
The client has three possible network messages that it will send to the server:
- store  
- get  - end
Where store tells the server to store the  for the , get tells the server to send back the password for the specified , and end tells the server to end the program.
The following is an example output and input for the client:Welcome to the SENG2250 password manager client, you have the following options:
- store  
- get 
- end
>>> store example.com correct horse battery staple Password successfully stored.
You have the following options:
- store  
- get 
- end
>>> get example.com
Your password for example.com is correct horse battery staple
You have the following options:
- store  
- get 
- end
>>> end bye.
Password Manager Server
You will extend the server.py or Server.java file to handle the store and get commands received from the client.
When the server receives a store command, it will store the specified password such that it is mapped to the specified website. Afterwards it will send back the message "Password successfully stored."
When the server receives a get command, it will send back only the password that is mapped to the specified website.
The end command is already handled in the code you are extending, but its specifications are that on receiving an end command, it will send back "end okay" and quit the program.
Requirements: The following are the requirements for the entirety of Task 2,
•    Personal implementation of RSA, using only BigInteger in Java or the standard library in
Python. Computes n, ɸ(n), e, and d, in addition to encryption and decryption. Uses a personal implementation of the fast modular exponentiation algorithm where applicable. (10 Marks)
•    Extends the client program to have an interface that handles erroneous inputs by clearly telling the user what was wrong and taking them back to the main interface. (5 Marks)
•    Correctly handles passwords so that interceptors and the server are never able to clearly read them (20 Marks)
•    Extends the server to handle the store and get commands (4 Marks)
•   All sent messages use the sockets and follow the exact correct format: (6 Marks)
◦     Client: store                        Server: Password successfully stored
◦     Client: get                                                 Server: 
◦     Client: end                                                                   Server: end okay
Task 3: Reflections  (10 Marks)
For this task you will write two brief word reflections on Tasks 1 and 2. The two reflections will be 200- 500 words each and will firstly discuss what you have learnt from extra resources, such as websites, textbooks, or large language models, to complete the tasks. The reflections will then relate what you have learnt to subjects covered in our labs and lectures. To strengthen your reflection, you may also   either discuss how these tasks relate to real world applications, or how your programs resulting from these tasks may be extended to be better applicable in the real world.
Your reflection should cite the extra resources you learnt from, if any, including prompts from LLMs   (such as ChatGPT). Your bibliography should follow a citation standard such as IEEE, APA, or Harvard. The bibliography will not count towards your word count.
Your answers to the two reflective questions in Task 1 should also be included in this document.
Submission Guidelines
Submissions should be contained in a single zip file. This zip file will include the reflections document in a pdf format, and two folders called “task 1” and “task 2” . The two folders will contain all your certificates, code and external files required to run your programs for the respective tasks, they also will contain a “ README.md” file which states instructions for setting up and running your programs.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
