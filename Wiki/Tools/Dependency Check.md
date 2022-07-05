# Dependency Check

## Beispiele für Reports

- CVE-2022-24434 (OSSINDEX)
This affects all versions of package notevil; all versions of package argencoders-notevil. It is vulnerable to Sandbox Escape leading to Prototype pollution. The package fails to restrict access to the main context, allowing an attacker to add or modify an object's prototype. **Note:** This vulnerability derives from an incomplete fix in [SNYK-JS-NOTEVIL-608878](https://security.snyk.io/vuln/SNYK-JS-NOTEVIL-608878). 

CWE-1321

CVSSv2: 
	• Base Score: MEDIUM (6.4) 
	• Vector: /AV:N/AC:L/Au:N/C:P/I:P/A:N CVSSv3: 
	• Base Score: MEDIUM (6.5) 
	• Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:L/A:N 
	
References: 
	• MISC - https://snyk.io/vuln/SNYK-JS-ARGENCODERSNOTEVIL-2388587 
	• MISC - https://snyk.io/vuln/SNYK-JS-NOTEVIL-2385946 
	
• OSSINDEX - [CVE-2021-23771] This affects all versions of package notevil; all versions of package argencoders-notevil. It is vulnerable to Sandbox Escape leading to Prototype pollution. The package fails to restrict access to the main context, allowing an attacker to add or modify an object's prototype. 
**Note:** This vulnerability derives from an incomplete fix in [SNYK-JS-NOTEVIL-608878](https://security.snyk.io/vuln/SNYKJS-NOTEVIL-608878).

• OSSIndex - http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2021-23771
• OSSIndex - https://github.com/mmckegg/notevil/blob/master/lib/primitives.js#L24 

Vulnerable Software & Versions: (show all) 
• cpe:2.3:a:notevil_project:notevil:*:*:*:*:*:node.js:*:* versions up to (including) 1.3.3