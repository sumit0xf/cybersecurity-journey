# WannaCry Ransomware and EternalBlue (MS17-010)

WannaCry is a ransomware worm that caused a massive global cyberattack in May 2017. It encrypted files on infected computers and demanded a ransom payment in Bitcoin to restore access. The attack affected hospitals, businesses, government organizations, and individual users across more than 150 countries.

WannaCry spread using a vulnerability in Microsoft's Server Message Block (SMB) protocol known as **MS17-010**. The exploit used to attack this vulnerability was called **EternalBlue**. EternalBlue exploited a flaw in SMBv1 that allowed attackers to execute code remotely without authentication. Once a machine was compromised, WannaCry automatically scanned for other vulnerable systems and infected them, allowing it to spread rapidly across networks.

In my WannaCry lab, I observed how the malware exploited the SMB vulnerability to gain access to a target system. I learned how ransomware encrypts files, displays ransom messages, and attempts to spread to other vulnerable machines. The lab demonstrated the importance of understanding both vulnerabilities and malware behavior in a controlled environment.

Microsoft released the **MS17-010 security patch** before the WannaCry outbreak. Systems that installed this patch were protected because the vulnerability exploited by EternalBlue was fixed. Organizations that failed to update their systems remained vulnerable and were heavily impacted by the attack. This highlights the importance of regular patch management, vulnerability assessment, system updates, and maintaining security best practices to reduce the risk of large-scale cyberattacks.

### Key Takeaways

* Understand how ransomware operates.
* Learn how EternalBlue exploited SMBv1.
* Recognize the importance of timely patching.
* Appreciate the role of security updates in preventing cyberattacks.
* Understand how worms can spread automatically across networks.
