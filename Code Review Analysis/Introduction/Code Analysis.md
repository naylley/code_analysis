### -Types of code review
#### 1.Static Code Review
#### 2.Dynamic code Review
# Static Code Analysis
Static code analysis is a technique of analyzing the source code of a software program without actually executing it. In static code analysis, software tools are used to examine the code for potential issues, such as security vulnerabilities, coding errors, and performance bottlenecks.

Static code analysis tools use various techniques to identify issues in the code. Some tools use pattern matching to detect coding errors or security issues based on known coding patterns that are often problematic. Other tools use code metrics to identify issues such as code complexity, which can affect performance and maintainability. Additionally, some tools use formal methods to analyze the code mathematically and prove that the code is correct.

Static code analysis can be performed automatically using specialized tools, which can scan the code quickly and efficiently to identify potential issues. The use of static code analysis can help developers catch issues early in the development process, reducing the cost and effort required to fix them later. It can also improve the overall quality of the code, making it more efficient, maintainable, and secure.

Static analysis is a software testing technique that involves examining the source code or compiled code of a program without actually executing it. The goal of static analysis is to identify potential defects and security vulnerabilities in the code by analyzing its syntax, structure, and data flow.

Static analysis is commonly used in software development to identify coding errors early in the development process, before the code is deployed to production. It can help developers catch errors and vulnerabilities that might otherwise be missed during manual code reviews or testing.

There are two main types of static analysis:

1.  Static code analysis: This involves analyzing the source code of a program to identify issues such as syntax errors, logic errors, code smells, and other issues that might impact the program's performance or security. Static code analysis can be done manually or using automated tools.
    
2.  Static binary analysis: This involves analyzing the compiled code of a program to identify issues such as buffer overflows, memory leaks, and other vulnerabilities. Static binary analysis is often used in security testing to identify vulnerabilities in software that might be used by attackers to exploit a system.

### Source Code Sources
Some of the location an analyst can obtain source code includes;
1. Cloud Market Place
2. Docker Hub
3. Contact product sales personnel
4. Freelance software
5. Mobile application stores e.g playstore


### Tips for Conducting a comprehesive source code review
1. Understand how to develop similar basic application e.g how to develop a booking php based application , an express based banking application, a spring boot online delivery app etc.Getting basic understanding of the language such as varilables,functions,objects,functions would help in understanding the code,
2. Learn about common vulnerabilities and get familiar with  these vulnerabilities signatures
4.  Obtain a list of common dangerous functions used in the application stack e.g common risky PHP,C ,Java,Python functions.e.g from OWASP cheat sheet, htb academy,pentester lab etc
5. Understand the main functions provided by the applications especially thise that might be critical to business e.g users,user permissions,business impact of each application feature,Authentication ,shipping,payment,etc
6.  Obtain the applications source codes .e.g from the sources mentioned above.
7. Run automated  SAST tools against the application source code e.g SEMGREP,graudit,code ql,sonar cube.
8. Through manual validation of output obtained from step 6;
10. Do recon the code base e.g identigy all the routes i.e web.xml,routes.rb etc.
11. Grep the common vulnerabilties listed below e.g user,password,key,secret,db,basic auth credentials,encryption keys,digital certificates,custom secrets.Further do regex search eg for AWS Keys search AIK[0-9A-Z]{16}.
12. List the applications  sources and sinks.Sources are sections where data is inputted and sinks are where data is being processed(especially check for the processing of user/attacker controlled data processing).
13. Spend some time to map data flow from the sources to the sinks.
14. Map the routes to the server side functionalityand make anote of the input for each routes.
15. Go through a server-side flow from HTTPrequest(source) to the  pointin code where it os being processed(sink) and repeat the process for all other attack surface.
16. Conduct an entropy analysis.

Further analysis include;
15. Understand interoperation within the software and map out the potential attack surface throughly.
16. Review the dependencies that are used within a project .Audit these dependencies using SCA tools, analyis binaries etc.Search for outdated dependencies.
17. Avoid making assumptions especially for standard libraries ...read their documentation and code to fully comprehend how functionality is being provided.
18. Cover all attack surfaces externally and internally (services,protovols,ports)
19. For any uncovered vulnerabilities make an effort to chain the vulnerabilities to have better impact explanation,
20. Gain a deep understanding about an application and its stack by reading documentation.
21. Identify security considerations that software developers need to be aware when developing software.

### Common code analysis
1. SEMGREP
2. Graudit 
3. codeql
4. Truffle hog
5. Git leaks
6. secret scanner


### Some of the vulnerabilities identified via Code Review include
1. Owasp top 10 web /mobile vulenerabilities.
2. Information leaks e.g internal urls,API,Password
3. Hardcoded credentials.
4. API Keys
5. Application logic flaws.
6. Other bad security practices e.g blacklist
7. Configuration issues
8. Weak  cryptography utiliation e.g grep for MD5,DES,SHA1 etc.

Conclusion
For unfamiliar frameworks read for security features provided by the framework.
For obsuficated code do deobsufcation prior to analysis.
In some cases CSRF tokens might only be checked on the client side and not server side.
Some developer comments might be resourceful in revealing sensitive info.
Use a similar approach for mobile applications however consider the common mobile applications issues .

Practise -https://github.com/ShiftLeftSecurity/tarpit-java
https://semgrep.dev/

