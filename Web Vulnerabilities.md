## Top Web Vulnerabilities
-------------------------------- Author: Hacking Heroes
-------------------------------- Modified By: Muhfat Alam

### ⭐️ Injection Vulnerabilities
1. SQL Injection (SQLi)
2. Cross-Site Scripting (XSS)
3. Cross-Site Request Forgery (CSRF)
4. Remote Code Injection (RCE)
5. Command Injection [^1]
6. XML Injection
7. LDAP Injection
8. XPath Injection
9. HTML Injection
10. Server-Side Includes (SSI) Injection
11. OS Command Injection
12. Blind SQL Injection
13. Server-Side Template Injection (SSTI)


### ⭐️ Broken Authentication and Session Management
14. Session Fixation
15. Brute-Force Attack
16. Session Hijacking
17. Password Cracking
18. Weak Password Storage
19. Insecure Authentication
20. Cookie Theft
21. Credential Reuse


### ⭐️ Sensitive Data Exposure:
22. Inadequate Encryption
23. Insecure Direct Object References (IDOR)
24. Data Leakage
25. Unencrypted Data Storage
26. Missing Security Header
27. Insecure File Handling


### ⭐️ Security Misconfiguration:
28. Default Passwords
29. Directory Listing
30. Unprotected API Endpoints
31. Open Ports
32. Unpatched Software


### ⭐️ Broken Access Control:
33. Privilege Escalation
34. Insecure Direct Object References
35. Missing Function-Level Access Control


### ⭐️ Insecure Deserialization
36. Remote Code Execution via Deserialization
37. Data Tampering
38. Object Injection


### ⭐️ API Security
39. Insecure API Endpoints
40. API key Exposure
41. Lack of Rate Limiting
42. Inadequate Input Validation


### ⭐️ Insecure Communication
43. Man-In-the-Middle (MITM) Attack
44. Insufficient Transport Layer Security
45. Insufficient SSL/TLS Configuration
46. Insecure Communication Protocols


### ⭐️ Client-Side Vulnerability
47. DOM-Based XSS (DOM = Document Object Model)
48. Insecure Cross-Origin Communication
49. Browser Caches Poisoning
50. Clickjacking


### ⭐️ Denial of Service (DoS)
51. Distributed Denial of Service (DDoS)
52. Application Layer DoS
53. Slowloris Attack  [^2]
54. XML Denial of Service


### ⭐️ Mobile Web Vulnerabilities:
55. Insecure Data Storage on Mobile Devices
56. Insecure Data Transmission on Mobile Devices
57. Insecure Mobile API Endpoints
58. Mobile App Reverse Engineering


### ⭐️ IoT Web Vulnerabilities
59. Insecure IoT Device Management
60. Weak Authentication to Smart Homes
61. IoT Data Privacy Issues


### ⭐️ Web of Things (WoT) Vulnerabilities:
62. Unauthorized Access to Smart Homes
63. IoT Data Privacy Issues


### ⭐️ Authentication Bypass
64. Insecure "Remember Me" Functionality
65. CAPTCHA Bypass


### ⭐️ Server-Side Request Forgery (SSRF)
66. Blind SSR
67. Time-Based Blind SSRF


### ⭐️ Content Spoofing
68. MIME Sniffing
69. X-Content-Type-Options Bypass
70. Content Security Policy (CSP) Bypass


### ⭐️ Business Logic Flaws:
71. Inconsistent Validation
72. Race Conditions
73. Order Processing Vulnerabilities
74. User-Based Flaws
75. Account Enumeration


### ⭐️ Zero-Day Vulnerabilities
76. Unknown Vulnerabilities
77. Unpatched Vulnerabilities
78. Day-Zero Exploits













[^1]: Command Injection: Command injection is an attack in which the goal is execution of arbitrary commands on the host operating system via a vulnerable application.
Example: The following code is a wrapper around the UNIX command cat which prints the contents of a file to standard output. It is also injectable:
        ```
        #include <stdio.h>
        #include <unistd.h>
        
        int main(int argc, char **argv) {
         char cat[] = "cat ";
         char *command;
         size_t commandLength;
        
         commandLength = strlen(cat) + strlen(argv[1]) + 1;
         command = (char *) malloc(commandLength);
         strncpy(command, cat, commandLength);
         strncat(command, argv[1], (commandLength - strlen(cat)) );
        
         system(command);
         return (0);
        }
        ```
        
        Used normally, the output is simply the contents of the file requested:
        
        ```
        $ ./catWrapper Story.txt
        When last we left our heroes...
        ```
        
        However, if we add a semicolon and another command to the end of this line, the command is executed by catWrapper with no complaint:
        
        ```
        $ ./catWrapper "Story.txt; ls"
        When last we left our heroes...
        Story.txt               doubFree.c              nullpointer.c
        unstosig.c              www*                    a.out*
        format.c                strlen.c                useFree*
        catWrapper*             misnull.c               strlength.c             useFree.c
        commandinjection.c      nodefault.c             trunc.c                 writeWhatWhere.c
        ```
        
        If catWrapper had been set to have a higher privilege level than the standard user, arbitrary commands could be executed with that higher privilege.



[^2]: Slowloris is a denial-of-service attack program which allows an attacker to overwhelm a targeted server by opening and maintaining many simultaneous HTTP connections between the attacker and the target.


![Screenshot 2024-07-23 at 4 33 48 PM](https://github.com/user-attachments/assets/c037a0f1-03b6-4c55-b381-4a0f7000eb80)

