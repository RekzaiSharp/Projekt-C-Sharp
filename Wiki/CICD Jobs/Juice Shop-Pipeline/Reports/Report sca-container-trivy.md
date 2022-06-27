# Report sca-container-trivy
````
{
  "version": "2.3",
  "vulnerabilities": [
    {
      "id": "NSWG-ECO-428",
      "category": "container_scanning",
      "message": "Out-of-bounds Read",
      "description": "`base64url` allocates uninitialized Buffers when number is passed in input on Node.js 4.x and below",
      "cve": "NSWG-ECO-428",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade base64url to >=3.0.0",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "base64url"
          },
          "version": "0.0.6"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "NSWG-ECO-428",
          "value": "NSWG-ECO-428",
          "url": "https://hackerone.com/reports/321687"
        }
      ],
      "links": [{
          "url": "https://github.com/brianloveswords/base64url/pull/25"
        },{
          "url": "https://hackerone.com/reports/321687"
        }
      ]
    },
    {
      "id": "GHSA-rvg8-pwq2-xj7q",
      "category": "container_scanning",
      "message": "Out-of-bounds Read in base64url",
      "description": "Versions of `base64url` before 3.0.0 are vulnerable to to out-of-bounds reads as it allocates uninitialized Buffers when number is passed in input on Node.js 4.x and below.\n\n\n## Recommendation\n\nUpdate to version 3.0.0 or later.",
      "cve": "GHSA-rvg8-pwq2-xj7q",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade base64url to 3.0.0",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "base64url"
          },
          "version": "0.0.6"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "GHSA-rvg8-pwq2-xj7q",
          "value": "GHSA-rvg8-pwq2-xj7q",
          "url": "https://github.com/advisories/GHSA-rvg8-pwq2-xj7q"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-rvg8-pwq2-xj7q"
        },{
          "url": "https://github.com/brianloveswords/base64url/pull/25"
        },{
          "url": "https://hackerone.com/reports/321687"
        },{
          "url": "https://www.npmjs.com/advisories/658"
        }
      ]
    },
    {
      "id": "CVE-2022-24434",
      "category": "container_scanning",
      "message": "Crash in HeaderParser in dicer",
      "description": "This affects all versions of package dicer. A malicious attacker can send a modified form to server, and crash the nodejs service. An attacker could sent the payload again and again so that the service continuously crashes.",
      "cve": "CVE-2022-24434",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "No solution provided",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "dicer"
          },
          "version": "0.2.5"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2022-24434",
          "value": "CVE-2022-24434",
          "url": "https://avd.aquasec.com/nvd/cve-2022-24434"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-wm7h-9275-46v2"
        },{
          "url": "https://github.com/mscdex/busboy/issues/250"
        },{
          "url": "https://github.com/mscdex/dicer/pull/22"
        },{
          "url": "https://github.com/mscdex/dicer/pull/22/commits/b7fca2e93e8e9d4439d8acc5c02f5e54a0112dac"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2022-24434"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-2838865"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-DICER-2311764"
        }
      ]
    },
    {
      "id": "CVE-2019-10775",
      "category": "container_scanning",
      "message": "Denial of Service in ecstatic",
      "description": "ecstatic have a denial of service vulnerability. Successful exploitation could lead to crash of an application.",
      "cve": "CVE-2019-10775",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade ecstatic to 4.1.3",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "ecstatic"
          },
          "version": "3.3.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2019-10775",
          "value": "CVE-2019-10775",
          "url": "https://avd.aquasec.com/nvd/cve-2019-10775"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-jc84-3g44-wf2q"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-10775"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-ECSTATIC-540354"
        }
      ]
    },
    {
      "id": "CVE-2020-15084",
      "category": "container_scanning",
      "message": "Authorization bypass in express-jwt",
      "description": "In express-jwt (NPM package) up and including version 5.3.3, the algorithms entry to be specified in the configuration is not being enforced. When algorithms is not specified in the configuration, with the combination of jwks-rsa, it may lead to authorization bypass. You are affected by this vulnerability if all of the following conditions apply: - You are using express-jwt - You do not have **algorithms** configured in your express-jwt configuration. - You are using libraries such as jwks-rsa as the **secret**. You can fix this by specifying **algorithms** in the express-jwt configuration. See linked GHSA for example. This is also fixed in version 6.0.0.",
      "cve": "CVE-2020-15084",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade express-jwt to 6.0.0",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "express-jwt"
          },
          "version": "0.1.3"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2020-15084",
          "value": "CVE-2020-15084",
          "url": "https://avd.aquasec.com/nvd/cve-2020-15084"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-6g6m-m6h5-w9gf"
        },{
          "url": "https://github.com/auth0/express-jwt/commit/7ecab5f8f0cab5297c2b863596566eb0c019cdef"
        },{
          "url": "https://github.com/auth0/express-jwt/security/advisories/GHSA-6g6m-m6h5-w9gf"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2020-15084"
        }
      ]
    },
    {
      "id": "CVE-2022-33987",
      "category": "container_scanning",
      "message": "The got package before 12.1.0 (also fixed in 11.8.5) for Node.js allow ...",
      "description": "The got package before 12.1.0 (also fixed in 11.8.5) for Node.js allows a redirect to a UNIX socket.",
      "cve": "CVE-2022-33987",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade got to 11.8.5, 12.1.0",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "got"
          },
          "version": "8.3.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2022-33987",
          "value": "CVE-2022-33987",
          "url": "https://avd.aquasec.com/nvd/cve-2022-33987"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-pfrx-2q88-qq97"
        },{
          "url": "https://github.com/sindresorhus/got/commit/861ccd9ac2237df762a9e2beed7edd88c60782dc"
        },{
          "url": "https://github.com/sindresorhus/got/compare/v12.0.3...v12.1.0"
        },{
          "url": "https://github.com/sindresorhus/got/pull/2047"
        },{
          "url": "https://github.com/sindresorhus/got/releases/tag/v11.8.5"
        },{
          "url": "https://github.com/sindresorhus/got/releases/tag/v12.1.0"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2022-33987"
        }
      ]
    },
    {
      "id": "CVE-2015-9235",
      "category": "container_scanning",
      "message": "nodejs-jsonwebtoken: verification step bypass with an altered token",
      "description": "In jsonwebtoken node module before 4.2.2 it is possible for an attacker to bypass verification when a token digitally signed with an asymmetric key (RS/ES family) of algorithms but instead the attacker send a token digitally signed with a symmetric algorithm (HS* family).",
      "cve": "CVE-2015-9235",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade jsonwebtoken to 4.2.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "jsonwebtoken"
          },
          "version": "0.1.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2015-9235",
          "value": "CVE-2015-9235",
          "url": "https://avd.aquasec.com/nvd/cve-2015-9235"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2015-9235"
        },{
          "url": "https://auth0.com/blog/2015/03/31/critical-vulnerabilities-in-json-web-token-libraries/"
        },{
          "url": "https://github.com/advisories/GHSA-c7hr-j4mj-j2w6"
        },{
          "url": "https://github.com/auth0/node-jsonwebtoken/commit/1bb584bc382295eeb7ee8c4452a673a77a68b687"
        },{
          "url": "https://nodesecurity.io/advisories/17"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2015-9235"
        },{
          "url": "https://www.npmjs.com/advisories/17"
        },{
          "url": "https://www.timmclean.net/2015/02/25/jwt-alg-none.html"
        }
      ]
    },
    {
      "id": "NSWG-ECO-17",
      "category": "container_scanning",
      "message": "Verification Bypass",
      "description": "It is possible for an attacker to bypass verification when \"a token digitally signed with an asymetric key (RS/ES family) of algorithms but instead the attacker send a token digitally signed with a symmetric algorithm (HS* family)\" [1]",
      "cve": "NSWG-ECO-17",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade jsonwebtoken to >=4.2.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "jsonwebtoken"
          },
          "version": "0.1.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "NSWG-ECO-17",
          "value": "NSWG-ECO-17",
          "url": ""
        }
      ],
      "links": [{
          "url": "https://auth0.com/blog/2015/03/31/critical-vulnerabilities-in-json-web-token-libraries/"
        },{
          "url": "https://github.com/auth0/node-jsonwebtoken/commit/1bb584bc382295eeb7ee8c4452a673a77a68b687"
        },{
          "url": "https://www.timmclean.net/2015/02/25/jwt-alg-none.html"
        }
      ]
    },
    {
      "id": "CVE-2015-9235",
      "category": "container_scanning",
      "message": "nodejs-jsonwebtoken: verification step bypass with an altered token",
      "description": "In jsonwebtoken node module before 4.2.2 it is possible for an attacker to bypass verification when a token digitally signed with an asymmetric key (RS/ES family) of algorithms but instead the attacker send a token digitally signed with a symmetric algorithm (HS* family).",
      "cve": "CVE-2015-9235",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade jsonwebtoken to 4.2.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "jsonwebtoken"
          },
          "version": "0.4.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2015-9235",
          "value": "CVE-2015-9235",
          "url": "https://avd.aquasec.com/nvd/cve-2015-9235"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2015-9235"
        },{
          "url": "https://auth0.com/blog/2015/03/31/critical-vulnerabilities-in-json-web-token-libraries/"
        },{
          "url": "https://github.com/advisories/GHSA-c7hr-j4mj-j2w6"
        },{
          "url": "https://github.com/auth0/node-jsonwebtoken/commit/1bb584bc382295eeb7ee8c4452a673a77a68b687"
        },{
          "url": "https://nodesecurity.io/advisories/17"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2015-9235"
        },{
          "url": "https://www.npmjs.com/advisories/17"
        },{
          "url": "https://www.timmclean.net/2015/02/25/jwt-alg-none.html"
        }
      ]
    },
    {
      "id": "NSWG-ECO-17",
      "category": "container_scanning",
      "message": "Verification Bypass",
      "description": "It is possible for an attacker to bypass verification when \"a token digitally signed with an asymetric key (RS/ES family) of algorithms but instead the attacker send a token digitally signed with a symmetric algorithm (HS* family)\" [1]",
      "cve": "NSWG-ECO-17",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade jsonwebtoken to >=4.2.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "jsonwebtoken"
          },
          "version": "0.4.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "NSWG-ECO-17",
          "value": "NSWG-ECO-17",
          "url": ""
        }
      ],
      "links": [{
          "url": "https://auth0.com/blog/2015/03/31/critical-vulnerabilities-in-json-web-token-libraries/"
        },{
          "url": "https://github.com/auth0/node-jsonwebtoken/commit/1bb584bc382295eeb7ee8c4452a673a77a68b687"
        },{
          "url": "https://www.timmclean.net/2015/02/25/jwt-alg-none.html"
        }
      ]
    },
    {
      "id": "CVE-2016-1000223",
      "category": "container_scanning",
      "message": "Forgeable Public/Private Tokens",
      "description": "Since \"algorithm\" isn't enforced in `jws.verify()`, a malicious user could choose what algorithm is sent to the server. If the server is expecting RSA but is sent HMAC-SHA with RSA's public key, the server will think the public key is actually an HMAC private key. This could be used to forge any data an attacker wants.\n\nIn addition, there is the `none` algorithm to be concerned about.  In versions prior to 3.0.0, verification of the token could be bypassed when the `alg` field is set to `none`.\n\n*Edit ( 7/29/16 ): A previous version of this advisory incorrectly stated that the vulnerability was patched in version 2.0.0 instead of 3.0.0. The advisory has been updated to reflect this new information. Thanks to Fabien Catteau for reporting the error.*",
      "cve": "CVE-2016-1000223",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade jws to >=3.0.0",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "jws"
          },
          "version": "0.2.6"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2016-1000223",
          "value": "CVE-2016-1000223",
          "url": "https://avd.aquasec.com/nvd/cve-2016-1000223"
        }
      ],
      "links": [{
          "url": "https://auth0.com/blog/2015/03/31/critical-vulnerabilities-in-json-web-token-libraries/"
        },{
          "url": "https://github.com/advisories/GHSA-gjcw-v447-2w7q"
        },{
          "url": "https://github.com/brianloveswords/node-jws/commit/585d0e1e97b6747c10cf5b7689ccc5618a89b299#diff-4ac32a78649ca5bdd8e0ba38b7006a1e"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2016-1000223"
        },{
          "url": "https://snyk.io/vuln/npm:jws:20160726"
        },{
          "url": "https://www.npmjs.com/advisories/88"
        }
      ]
    },
    {
      "id": "CVE-2019-10744",
      "category": "container_scanning",
      "message": "nodejs-lodash: prototype pollution in defaultsDeep function leading to modifying properties",
      "description": "Versions of lodash lower than 4.17.12 are vulnerable to Prototype Pollution. The function defaultsDeep could be tricked into adding or modifying properties of Object.prototype using a constructor payload.",
      "cve": "CVE-2019-10744",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to 4.17.12",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2019-10744",
          "value": "CVE-2019-10744",
          "url": "https://avd.aquasec.com/nvd/cve-2019-10744"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/errata/RHSA-2019:3024"
        },{
          "url": "https://access.redhat.com/security/cve/CVE-2019-10744"
        },{
          "url": "https://github.com/advisories/GHSA-jf85-cpcp-j695"
        },{
          "url": "https://github.com/lodash/lodash/pull/4336"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-10744"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20191004-0005/"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-LODASH-450202"
        },{
          "url": "https://support.f5.com/csp/article/K47105354?utm_source=f5support&amp;utm_medium=RSS"
        },{
          "url": "https://www.npmjs.com/advisories/1065"
        },{
          "url": "https://www.oracle.com/security-alerts/cpujan2021.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2020.html"
        }
      ]
    },
    {
      "id": "CVE-2018-16487",
      "category": "container_scanning",
      "message": "lodash: Prototype pollution in utilities function",
      "description": "A prototype pollution vulnerability was found in lodash <4.17.11 where the functions merge, mergeWith, and defaultsDeep can be tricked into adding or modifying properties of Object.prototype.",
      "cve": "CVE-2018-16487",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to >=4.17.11",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2018-16487",
          "value": "CVE-2018-16487",
          "url": "https://avd.aquasec.com/nvd/cve-2018-16487"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2018-16487"
        },{
          "url": "https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-16487"
        },{
          "url": "https://github.com/advisories/GHSA-4xc9-xhrj-v574"
        },{
          "url": "https://hackerone.com/reports/380873"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2018-16487"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20190919-0004/"
        },{
          "url": "https://www.npmjs.com/advisories/782"
        }
      ]
    },
    {
      "id": "CVE-2020-8203",
      "category": "container_scanning",
      "message": "nodejs-lodash: prototype pollution in zipObjectDeep function",
      "description": "Prototype pollution attack when using _.zipObjectDeep in lodash before 4.17.20.",
      "cve": "CVE-2020-8203",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to 4.17.20",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2020-8203",
          "value": "CVE-2020-8203",
          "url": "https://avd.aquasec.com/nvd/cve-2020-8203"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2020-8203"
        },{
          "url": "https://github.com/advisories/GHSA-p6mc-m468-83gw"
        },{
          "url": "https://github.com/lodash/lodash/commit/c84fe82760fb2d3e03a63379b297a1cc1a2fce12"
        },{
          "url": "https://github.com/lodash/lodash/issues/4744"
        },{
          "url": "https://github.com/lodash/lodash/issues/4874"
        },{
          "url": "https://hackerone.com/reports/712065"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2020-8203"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20200724-0006/"
        },{
          "url": "https://www.npmjs.com/advisories/1523"
        },{
          "url": "https://www.oracle.com//security-alerts/cpujul2021.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuApr2021.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuapr2022.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpujan2022.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-23337",
      "category": "container_scanning",
      "message": "nodejs-lodash: command injection via template",
      "description": "Lodash versions prior to 4.17.21 are vulnerable to Command Injection via the template function.",
      "cve": "CVE-2021-23337",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to 4.17.21",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-23337",
          "value": "CVE-2021-23337",
          "url": "https://avd.aquasec.com/nvd/cve-2021-23337"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-23337"
        },{
          "url": "https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-23337"
        },{
          "url": "https://github.com/advisories/GHSA-35jh-r3h4-6jhm"
        },{
          "url": "https://github.com/lodash/lodash/blob/ddfd9b11a0126db2302cb70ec9973b66baec0975/lodash.js#L14851"
        },{
          "url": "https://github.com/lodash/lodash/blob/ddfd9b11a0126db2302cb70ec9973b66baec0975/lodash.js%23L14851"
        },{
          "url": "https://github.com/lodash/lodash/commit/3469357cff396a26c363f8c1b5a91dde28ba4b1c"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-23337"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20210312-0006/"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGFUJIONWEBJARS-1074932"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARS-1074930"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSBOWER-1074928"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSBOWERGITHUBLODASH-1074931"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-1074929"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-LODASH-1040724"
        },{
          "url": "https://www.oracle.com//security-alerts/cpujul2021.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpujan2022.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2019-1010266",
      "category": "container_scanning",
      "message": "lodash: uncontrolled resource consumption in Data handler causing denial of service",
      "description": "lodash prior to 4.17.11 is affected by: CWE-400: Uncontrolled Resource Consumption. The impact is: Denial of service. The component is: Date handler. The attack vector is: Attacker provides very long strings, which the library attempts to match using a regular expression. The fixed version is: 4.17.11.",
      "cve": "CVE-2019-1010266",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to 4.17.11",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2019-1010266",
          "value": "CVE-2019-1010266",
          "url": "https://avd.aquasec.com/nvd/cve-2019-1010266"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2019-1010266"
        },{
          "url": "https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-1010266"
        },{
          "url": "https://github.com/advisories/GHSA-x5rq-j2xg-h7qm"
        },{
          "url": "https://github.com/lodash/lodash/commit/5c08f18d365b64063bfbfa686cbb97cdd6267347"
        },{
          "url": "https://github.com/lodash/lodash/issues/3359"
        },{
          "url": "https://github.com/lodash/lodash/wiki/Changelog"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2019-1010266"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20190919-0004/"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-LODASH-73639"
        }
      ]
    },
    {
      "id": "CVE-2020-28500",
      "category": "container_scanning",
      "message": "nodejs-lodash: ReDoS via the toNumber, trim and trimEnd functions",
      "description": "Lodash versions prior to 4.17.21 are vulnerable to Regular Expression Denial of Service (ReDoS) via the toNumber, trim and trimEnd functions.",
      "cve": "CVE-2020-28500",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to 4.17.21",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2020-28500",
          "value": "CVE-2020-28500",
          "url": "https://avd.aquasec.com/nvd/cve-2020-28500"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2020-28500"
        },{
          "url": "https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-28500"
        },{
          "url": "https://github.com/advisories/GHSA-29mw-wpgm-hmr9"
        },{
          "url": "https://github.com/lodash/lodash/blob/npm/trimEnd.js#L8"
        },{
          "url": "https://github.com/lodash/lodash/blob/npm/trimEnd.js%23L8"
        },{
          "url": "https://github.com/lodash/lodash/pull/5065"
        },{
          "url": "https://github.com/lodash/lodash/pull/5065/commits/02906b8191d3c100c193fe6f7b27d1c40f200bb7"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2020-28500"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20210312-0006/"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGFUJIONWEBJARS-1074896"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARS-1074894"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSBOWER-1074892"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSBOWERGITHUBLODASH-1074895"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-1074893"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-LODASH-1018905"
        },{
          "url": "https://www.oracle.com//security-alerts/cpujul2021.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpujan2022.html"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2018-3721",
      "category": "container_scanning",
      "message": "lodash: Prototype pollution in utilities function",
      "description": "lodash node module before 4.17.5 suffers from a Modification of Assumed-Immutable Data (MAID) vulnerability via defaultsDeep, merge, and mergeWith functions, which allows a malicious user to modify the prototype of \"Object\" via __proto__, causing the addition or modification of an existing property that will exist on all objects.",
      "cve": "CVE-2018-3721",
      "severity": "Low",
      "confidence": "Unknown",
      "solution": "Upgrade lodash to >=4.17.5",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "lodash"
          },
          "version": "2.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2018-3721",
          "value": "CVE-2018-3721",
          "url": "https://avd.aquasec.com/nvd/cve-2018-3721"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2018-3721"
        },{
          "url": "https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-3721"
        },{
          "url": "https://github.com/advisories/GHSA-fvqr-27wr-82fm"
        },{
          "url": "https://github.com/lodash/lodash/commit/d8e069cc3410082e44eb18fcf8e7f3d08ebe1d4a"
        },{
          "url": "https://hackerone.com/reports/310443"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2018-3721"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20190919-0004/"
        },{
          "url": "https://snyk.io/vuln/npm:lodash:20180130"
        },{
          "url": "https://www.npmjs.com/advisories/577"
        }
      ]
    },
    {
      "id": "GHSA-5mrr-rgp6-x4gr",
      "category": "container_scanning",
      "message": "Command Injection in marsdb",
      "description": "All versions of `marsdb` are vulnerable to Command Injection. In the `DocumentMatcher` class, selectors on `$where` clauses are passed to a Function constructor unsanitized. This allows attackers to run arbitrary commands in the system when the function is executed.\n\n\n## Recommendation\n\nNo fix is currently available. Consider using an alternative package until a fix is made available.",
      "cve": "GHSA-5mrr-rgp6-x4gr",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "No solution provided",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "marsdb"
          },
          "version": "0.6.11"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "GHSA-5mrr-rgp6-x4gr",
          "value": "GHSA-5mrr-rgp6-x4gr",
          "url": "https://github.com/advisories/GHSA-5mrr-rgp6-x4gr"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-5mrr-rgp6-x4gr"
        },{
          "url": "https://github.com/bkimminich/juice-shop/issues/1173"
        },{
          "url": "https://www.npmjs.com/advisories/1122"
        }
      ]
    },
    {
      "id": "CVE-2021-44906",
      "category": "container_scanning",
      "message": "minimist: prototype pollution",
      "description": "Minimist <=1.2.5 is vulnerable to Prototype Pollution via file index.js, function setKey() (lines 69-95).",
      "cve": "CVE-2021-44906",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade minimist to 1.2.6",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "minimist"
          },
          "version": "0.2.1"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-44906",
          "value": "CVE-2021-44906",
          "url": "https://avd.aquasec.com/nvd/cve-2021-44906"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-44906"
        },{
          "url": "https://github.com/Marynk/JavaScript-vulnerability-detection/blob/main/minimist%20PoC.zip"
        },{
          "url": "https://github.com/advisories/GHSA-xvch-5gv4-984h"
        },{
          "url": "https://github.com/substack/minimist/blob/master/index.js#L69"
        },{
          "url": "https://github.com/substack/minimist/issues/164"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-44906"
        },{
          "url": "https://security.snyk.io/vuln/SNYK-JS-MINIMIST-559764"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-MINIMIST-559764"
        },{
          "url": "https://stackoverflow.com/questions/8588563/adding-custom-properties-to-a-function/20278068#20278068"
        }
      ]
    },
    {
      "id": "CVE-2017-18214",
      "category": "container_scanning",
      "message": "nodejs-moment: Regular expression denial of service",
      "description": "The moment module before 2.19.3 for Node.js is prone to a regular expression denial of service via a crafted date string, a different vulnerability than CVE-2016-4055.",
      "cve": "CVE-2017-18214",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade moment to 2.19.3",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "moment"
          },
          "version": "2.0.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2017-18214",
          "value": "CVE-2017-18214",
          "url": "https://avd.aquasec.com/nvd/cve-2017-18214"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2017-18214"
        },{
          "url": "https://github.com/advisories/GHSA-446m-mv8f-q348"
        },{
          "url": "https://github.com/moment/moment/issues/4163"
        },{
          "url": "https://github.com/moment/moment/pull/4326"
        },{
          "url": "https://nodesecurity.io/advisories/532"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2017-18214"
        },{
          "url": "https://www.npmjs.com/advisories/532"
        },{
          "url": "https://www.tenable.com/security/tns-2019-02"
        }
      ]
    },
    {
      "id": "CVE-2022-24785",
      "category": "container_scanning",
      "message": "Moment.js: Path traversal  in moment.locale",
      "description": "Moment.js is a JavaScript date library for parsing, validating, manipulating, and formatting dates. A path traversal vulnerability impacts npm (server) users of Moment.js between versions 1.0.1 and 2.29.1, especially if a user-provided locale string is directly used to switch moment locale. This problem is patched in 2.29.2, and the patch can be applied to all affected versions. As a workaround, sanitize the user-provided locale name before passing it to Moment.js.",
      "cve": "CVE-2022-24785",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade moment to 2.29.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "moment"
          },
          "version": "2.0.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2022-24785",
          "value": "CVE-2022-24785",
          "url": "https://avd.aquasec.com/nvd/cve-2022-24785"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2022-24785"
        },{
          "url": "https://github.com/advisories/GHSA-8hfj-j24r-96c4"
        },{
          "url": "https://github.com/moment/moment/commit/4211bfc8f15746be4019bba557e29a7ba83d54c5"
        },{
          "url": "https://github.com/moment/moment/security/advisories/GHSA-8hfj-j24r-96c4"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2022-24785"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20220513-0006/"
        },{
          "url": "https://www.tenable.com/security/tns-2022-09"
        }
      ]
    },
    {
      "id": "CVE-2016-4055",
      "category": "container_scanning",
      "message": "moment.js: regular expression denial of service",
      "description": "The duration function in the moment package before 2.11.2 for Node.js allows remote attackers to cause a denial of service (CPU consumption) via a long string, aka a \"regular expression Denial of Service (ReDoS).\"",
      "cve": "CVE-2016-4055",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade moment to >=2.11.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "moment"
          },
          "version": "2.0.0"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2016-4055",
          "value": "CVE-2016-4055",
          "url": "https://avd.aquasec.com/nvd/cve-2016-4055"
        }
      ],
      "links": [{
          "url": "http://www.openwall.com/lists/oss-security/2016/04/20/11"
        },{
          "url": "http://www.oracle.com/technetwork/security-advisory/cpujul2018-4258247.html"
        },{
          "url": "http://www.securityfocus.com/bid/95849"
        },{
          "url": "https://access.redhat.com/security/cve/CVE-2016-4055"
        },{
          "url": "https://github.com/advisories/GHSA-87vv-r9j6-g5qv"
        },{
          "url": "https://lists.apache.org/thread.html/10f0f3aefd51444d1198c65f44ffdf2d78ca3359423dbc1c168c9731@%3Cdev.flink.apache.org%3E"
        },{
          "url": "https://lists.apache.org/thread.html/17ff53f7999e74fbe3cc0ceb4e1c3b00b180b7c5afec8e978837bc49@%3Cuser.flink.apache.org%3E"
        },{
          "url": "https://lists.apache.org/thread.html/52bafac05ad174000ea465fe275fd3cc7bd5c25535a7631c0bc9bfb2@%3Cuser.flink.apache.org%3E"
        },{
          "url": "https://lists.apache.org/thread.html/54df3aeb4239b64b50b356f0ca6f986e3c4ca5b84c515dce077c7854@%3Cuser.flink.apache.org%3E"
        },{
          "url": "https://nodesecurity.io/advisories/55"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2016-4055"
        },{
          "url": "https://www.npmjs.com/advisories/55"
        },{
          "url": "https://www.owasp.org/index.php/Regular_expression_Denial_of_Service_-_ReDoS"
        },{
          "url": "https://www.tenable.com/security/tns-2019-02"
        }
      ]
    },
    {
      "id": "CVE-2022-21213",
      "category": "container_scanning",
      "message": "Prototype Pollution in mout",
      "description": "This affects all versions of package mout. The deepFillIn function can be used to 'fill missing properties recursively', while the deepMixIn mixes objects into the target object, recursively mixing existing child objects as well. In both cases, the key used to access the target object recursively is not checked, leading to exploiting this vulnerability. **Note:** This vulnerability derives from an incomplete fix of [CVE-2020-7792](https://security.snyk.io/vuln/SNYK-JS-MOUT-1014544).",
      "cve": "CVE-2022-21213",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "No solution provided",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "mout"
          },
          "version": "1.2.3"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2022-21213",
          "value": "CVE-2022-21213",
          "url": "https://avd.aquasec.com/nvd/cve-2022-21213"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-vvv8-xw5f-3f88"
        },{
          "url": "https://github.com/mout/mout/blob/master/src/object/deepFillIn.js"
        },{
          "url": "https://github.com/mout/mout/blob/master/src/object/deepMixIn.js"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2022-21213"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARS-2870623"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-2870622"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-MOUT-2342654"
        }
      ]
    },
    {
      "id": "CVE-2021-23566",
      "category": "container_scanning",
      "message": "nanoid: Information disclosure via valueOf() function",
      "description": "The package nanoid from 3.0.0 and before 3.1.31 are vulnerable to Information Exposure via the valueOf() function which allows to reproduce the last id generated.",
      "cve": "CVE-2021-23566",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade nanoid to 3.1.31",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "nanoid"
          },
          "version": "3.1.20"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-23566",
          "value": "CVE-2021-23566",
          "url": "https://avd.aquasec.com/nvd/cve-2021-23566"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-23566"
        },{
          "url": "https://gist.github.com/artalar/bc6d1eb9a3477d15d2772e876169a444"
        },{
          "url": "https://github.com/advisories/GHSA-qrpm-p2h7-hrv2"
        },{
          "url": "https://github.com/ai/nanoid/commit/2b7bd9332bc49b6330c7ddb08e5c661833db2575"
        },{
          "url": "https://github.com/ai/nanoid/pull/328"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-23566"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-2332550"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-NANOID-2332193"
        }
      ]
    },
    {
      "id": "CVE-2021-23771",
      "category": "container_scanning",
      "message": "Sandbox escape in notevil and argencoders-notevil",
      "description": "This affects all versions of package notevil; all versions of package argencoders-notevil. It is vulnerable to Sandbox Escape leading to Prototype pollution. The package fails to restrict access to the main context, allowing an attacker to add or modify an object's prototype. **Note:** This vulnerability derives from an incomplete fix in [SNYK-JS-NOTEVIL-608878](https://security.snyk.io/vuln/SNYK-JS-NOTEVIL-608878).",
      "cve": "CVE-2021-23771",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "No solution provided",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "notevil"
          },
          "version": "1.3.3"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-23771",
          "value": "CVE-2021-23771",
          "url": "https://avd.aquasec.com/nvd/cve-2021-23771"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-8g4m-cjm2-96wq"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-23771"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-ARGENCODERSNOTEVIL-2388587"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-NOTEVIL-2385946"
        }
      ]
    },
    {
      "id": "CVE-2016-1000237",
      "category": "container_scanning",
      "message": "XSS - Sanitization not applied recursively",
      "description": "sanitize-html before 1.4.3 has XSS.",
      "cve": "CVE-2016-1000237",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade sanitize-html to >=1.4.3",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sanitize-html"
          },
          "version": "1.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2016-1000237",
          "value": "CVE-2016-1000237",
          "url": "https://avd.aquasec.com/nvd/cve-2016-1000237"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-3j7m-hmh3-9jmp"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/commit/762fbc7bba389f3f789cc291c1eb2b64f60f2caf"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/issues/29"
        },{
          "url": "https://github.com/punkave/sanitize-html/issues/29"
        },{
          "url": "https://nodesecurity.io/advisories/135"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2016-1000237"
        },{
          "url": "https://raw.githubusercontent.com/distributedweaknessfiling/cvelist/master/2016/1000xxx/CVE-2016-1000237.json"
        },{
          "url": "https://www.npmjs.com/advisories/135"
        }
      ]
    },
    {
      "id": "CVE-2017-16016",
      "category": "container_scanning",
      "message": "Cross-Site Scripting in sanitize-html",
      "description": "Sanitize-html is a library for scrubbing html input of malicious values. Versions 1.11.1 and below are vulnerable to cross site scripting (XSS) in certain scenarios: If allowed at least one nonTextTags, the result is a potential XSS vulnerability.",
      "cve": "CVE-2017-16016",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade sanitize-html to 1.11.4",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sanitize-html"
          },
          "version": "1.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2017-16016",
          "value": "CVE-2017-16016",
          "url": "https://avd.aquasec.com/nvd/cve-2017-16016"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-xc6g-ggrc-qq4r"
        },{
          "url": "https://github.com/punkave/sanitize-html/commit/5d205a1005ba0df80e21d8c64a15bb3accdb2403"
        },{
          "url": "https://github.com/punkave/sanitize-html/commit/5d205a1005ba0df80e21d8c64a15bb3accdb2403)))"
        },{
          "url": "https://github.com/punkave/sanitize-html/issues/100"
        },{
          "url": "https://nodesecurity.io/advisories/154"
        },{
          "url": "https://npmjs.com/package/sanitize-html#discarding-the-entire-contents-of-a-disallowed-tag"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2017-16016"
        },{
          "url": "https://www.npmjs.com/advisories/154"
        }
      ]
    },
    {
      "id": "CVE-2021-26539",
      "category": "container_scanning",
      "message": "sanitize-html: improper handling of internationalized domain name (IDN) can lead to bypass hostname whitelist validation",
      "description": "Apostrophe Technologies sanitize-html before 2.3.1 does not properly handle internationalized domain name (IDN) which could allow an attacker to bypass hostname whitelist validation set by the \"allowedIframeHostnames\" option.",
      "cve": "CVE-2021-26539",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade sanitize-html to 2.3.1",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sanitize-html"
          },
          "version": "1.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-26539",
          "value": "CVE-2021-26539",
          "url": "https://avd.aquasec.com/nvd/cve-2021-26539"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-26539"
        },{
          "url": "https://advisory.checkmarx.net/advisory/CX-2021-4308"
        },{
          "url": "https://github.com/advisories/GHSA-rjqq-98f6-6j3r"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/blob/main/CHANGELOG.md#231-2021-01-22"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/pull/458"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-26539"
        }
      ]
    },
    {
      "id": "CVE-2021-26540",
      "category": "container_scanning",
      "message": "sanitize-html: improper validation of hostnames set by the \"allowedIframeHostnames\" option can lead to bypass hostname whitelist for iframe element",
      "description": "Apostrophe Technologies sanitize-html before 2.3.2 does not properly validate the hostnames set by the \"allowedIframeHostnames\" option when the \"allowIframeRelativeUrls\" is set to true, which allows attackers to bypass hostname whitelist for iframe element, related using an src value that starts with \"/\\\\example.com\".",
      "cve": "CVE-2021-26540",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade sanitize-html to 2.3.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sanitize-html"
          },
          "version": "1.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-26540",
          "value": "CVE-2021-26540",
          "url": "https://avd.aquasec.com/nvd/cve-2021-26540"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-26540"
        },{
          "url": "https://advisory.checkmarx.net/advisory/CX-2021-4309"
        },{
          "url": "https://github.com/advisories/GHSA-mjxr-4v3x-q3m4"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/blob/main/CHANGELOG.md#232-2021-01-26"
        },{
          "url": "https://github.com/apostrophecms/sanitize-html/pull/460"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-26540"
        }
      ]
    },
    {
      "id": "NSWG-ECO-154",
      "category": "container_scanning",
      "message": "Cross Site Scripting",
      "description": "Sanitize-html is a library for scrubbing html input of malicious values.\n\nVersions 1.11.1 and below are vulnerable to cross site scripting (XSS) in certain scenarios:\n\nIf allowed at least one nonTextTags, the result is a potential XSS vulnerability.\nPoC:\n\n```\nvar sanitizeHtml = require('sanitize-html');\n\nvar dirty = '!<textarea>&lt;/textarea&gt;<svg/onload=prompt`xs`&gt;</textarea>!';\nvar clean = sanitizeHtml(dirty, {\n    allowedTags: [ 'textarea' ]\n});\n\nconsole.log(clean);\n\n// !<textarea></textarea><svg/onload=prompt`xs`></textarea>!\n```",
      "cve": "NSWG-ECO-154",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade sanitize-html to >=1.11.4",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sanitize-html"
          },
          "version": "1.4.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "NSWG-ECO-154",
          "value": "NSWG-ECO-154",
          "url": ""
        }
      ],
      "links": [{
          "url": "https://github.com/punkave/sanitize-html/commit/5d205a1005ba0df80e21d8c64a15bb3accdb2403"
        },{
          "url": "https://github.com/punkave/sanitize-html/issues/100"
        }
      ]
    },
    {
      "id": "CVE-2022-21227",
      "category": "container_scanning",
      "message": "sqlite3: Denial of Service (DoS) in sqlite3",
      "description": "The package sqlite3 before 5.0.3 are vulnerable to Denial of Service (DoS) which will invoke the toString function of the passed parameter. If passed an invalid Function object it will throw and crash the V8 engine.",
      "cve": "CVE-2022-21227",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade sqlite3 to 5.0.3",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "sqlite3"
          },
          "version": "5.0.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2022-21227",
          "value": "CVE-2022-21227",
          "url": "https://avd.aquasec.com/nvd/cve-2022-21227"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2022-21227"
        },{
          "url": "https://github.com/TryGhost/node-sqlite3/commit/593c9d498be2510d286349134537e3bf89401c4a"
        },{
          "url": "https://github.com/TryGhost/node-sqlite3/issues/1440"
        },{
          "url": "https://github.com/TryGhost/node-sqlite3/issues/1449"
        },{
          "url": "https://github.com/TryGhost/node-sqlite3/security/advisories/GHSA-9qrh-qjmc-5w2p"
        },{
          "url": "https://github.com/advisories/GHSA-9qrh-qjmc-5w2p"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2022-21227"
        },{
          "url": "https://security.snyk.io/vuln/SNYK-JS-SQLITE3-2388645"
        },{
          "url": "https://snyk.io/vuln/SNYK-JAVA-ORGWEBJARSNPM-2805470"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-SQLITE3-2388645"
        }
      ]
    },
    {
      "id": "CVE-2021-32803",
      "category": "container_scanning",
      "message": "nodejs-tar: Insufficient symlink protection allowing arbitrary file creation and overwrite",
      "description": "The npm package \"tar\" (aka node-tar) before versions 6.1.2, 5.0.7, 4.4.15, and 3.2.3 has an arbitrary File Creation/Overwrite vulnerability via insufficient symlink protection. `node-tar` aims to guarantee that any file whose location would be modified by a symbolic link is not extracted. This is, in part, achieved by ensuring that extracted directories are not symlinks. Additionally, in order to prevent unnecessary `stat` calls to determine whether a given path is a directory, paths are cached when directories are created. This logic was insufficient when extracting tar files that contained both a directory and a symlink with the same name as the directory. This order of operations resulted in the directory being created and added to the `node-tar` directory cache. When a directory is present in the directory cache, subsequent calls to mkdir for that directory are skipped. However, this is also where `node-tar` checks for symlinks occur. By first creating a directory, and then replacing that directory with a symlink, it was thus possible to bypass `node-tar` symlink checks on directories, essentially allowing an untrusted tar file to symlink into an arbitrary location and subsequently extracting arbitrary files into that location, thus allowing arbitrary file creation and overwrite. This issue was addressed in releases 3.2.3, 4.4.15, 5.0.7 and 6.1.2.",
      "cve": "CVE-2021-32803",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade tar to 6.1.2, 5.0.7, 4.4.15, 3.2.3",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "tar"
          },
          "version": "2.2.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-32803",
          "value": "CVE-2021-32803",
          "url": "https://avd.aquasec.com/nvd/cve-2021-32803"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-32803"
        },{
          "url": "https://cert-portal.siemens.com/productcert/pdf/ssa-389290.pdf"
        },{
          "url": "https://errata.almalinux.org/8/ALSA-2021-3666.html"
        },{
          "url": "https://github.com/advisories/GHSA-r628-mhmh-qjhw"
        },{
          "url": "https://github.com/npm/node-tar/commit/9dbdeb6df8e9dbd96fa9e84341b9d74734be6c20"
        },{
          "url": "https://github.com/npm/node-tar/security/advisories/GHSA-r628-mhmh-qjhw"
        },{
          "url": "https://linux.oracle.com/cve/CVE-2021-32803.html"
        },{
          "url": "https://linux.oracle.com/errata/ELSA-2021-3666.html"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-32803"
        },{
          "url": "https://www.npmjs.com/advisories/1771"
        },{
          "url": "https://www.npmjs.com/package/tar"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-32804",
      "category": "container_scanning",
      "message": "nodejs-tar: Insufficient absolute path sanitization allowing arbitrary file creation and overwrite",
      "description": "The npm package \"tar\" (aka node-tar) before versions 6.1.1, 5.0.6, 4.4.14, and 3.3.2 has a arbitrary File Creation/Overwrite vulnerability due to insufficient absolute path sanitization. node-tar aims to prevent extraction of absolute file paths by turning absolute paths into relative paths when the `preservePaths` flag is not set to `true`. This is achieved by stripping the absolute path root from any absolute file paths contained in a tar file. For example `/home/user/.bashrc` would turn into `home/user/.bashrc`. This logic was insufficient when file paths contained repeated path roots such as `////home/user/.bashrc`. `node-tar` would only strip a single path root from such paths. When given an absolute file path with repeating path roots, the resulting path (e.g. `///home/user/.bashrc`) would still resolve to an absolute path, thus allowing arbitrary file creation and overwrite. This issue was addressed in releases 3.2.2, 4.4.14, 5.0.6 and 6.1.1. Users may work around this vulnerability without upgrading by creating a custom `onentry` method which sanitizes the `entry.path` or a `filter` method which removes entries with absolute paths. See referenced GitHub Advisory for details. Be aware of CVE-2021-32803 which fixes a similar bug in later versions of tar.",
      "cve": "CVE-2021-32804",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade tar to 6.1.1, 5.0.6, 4.4.14, 3.2.2",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "tar"
          },
          "version": "2.2.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-32804",
          "value": "CVE-2021-32804",
          "url": "https://avd.aquasec.com/nvd/cve-2021-32804"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-32804"
        },{
          "url": "https://cert-portal.siemens.com/productcert/pdf/ssa-389290.pdf"
        },{
          "url": "https://errata.almalinux.org/8/ALSA-2021-3666.html"
        },{
          "url": "https://github.com/advisories/GHSA-3jfq-g458-7qm9"
        },{
          "url": "https://github.com/npm/node-tar/commit/1f036ca23f64a547bdd6c79c1a44bc62e8115da4"
        },{
          "url": "https://github.com/npm/node-tar/security/advisories/GHSA-3jfq-g458-7qm9"
        },{
          "url": "https://linux.oracle.com/cve/CVE-2021-32804.html"
        },{
          "url": "https://linux.oracle.com/errata/ELSA-2021-3666.html"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-32804"
        },{
          "url": "https://www.npmjs.com/advisories/1770"
        },{
          "url": "https://www.npmjs.com/package/tar"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-37701",
      "category": "container_scanning",
      "message": "nodejs-tar: Insufficient symlink protection due to directory cache poisoning using symbolic links allowing arbitrary file creation and overwrite",
      "description": "The npm package \"tar\" (aka node-tar) before versions 4.4.16, 5.0.8, and 6.1.7 has an arbitrary file creation/overwrite and arbitrary code execution vulnerability. node-tar aims to guarantee that any file whose location would be modified by a symbolic link is not extracted. This is, in part, achieved by ensuring that extracted directories are not symlinks. Additionally, in order to prevent unnecessary stat calls to determine whether a given path is a directory, paths are cached when directories are created. This logic was insufficient when extracting tar files that contained both a directory and a symlink with the same name as the directory, where the symlink and directory names in the archive entry used backslashes as a path separator on posix systems. The cache checking logic used both `\\` and `/` characters as path separators, however `\\` is a valid filename character on posix systems. By first creating a directory, and then replacing that directory with a symlink, it was thus possible to bypass node-tar symlink checks on directories, essentially allowing an untrusted tar file to symlink into an arbitrary location and subsequently extracting arbitrary files into that location, thus allowing arbitrary file creation and overwrite. Additionally, a similar confusion could arise on case-insensitive filesystems. If a tar archive contained a directory at `FOO`, followed by a symbolic link named `foo`, then on case-insensitive file systems, the creation of the symbolic link would remove the directory from the filesystem, but _not_ from the internal directory cache, as it would not be treated as a cache hit. A subsequent file entry within the `FOO` directory would then be placed in the target of the symbolic link, thinking that the directory had already been created. These issues were addressed in releases 4.4.16, 5.0.8 and 6.1.7. The v3 branch of node-tar has been deprecated and did not receive patches for these issues. If you are still using a v3 release we recommend you update to a more recent version of node-tar. If this is not possible, a workaround is available in the referenced GHSA-9r2w-394v-53qc.",
      "cve": "CVE-2021-37701",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade tar to 6.1.7, 5.0.8, 4.4.16",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "tar"
          },
          "version": "2.2.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-37701",
          "value": "CVE-2021-37701",
          "url": "https://avd.aquasec.com/nvd/cve-2021-37701"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-37701"
        },{
          "url": "https://cert-portal.siemens.com/productcert/pdf/ssa-389290.pdf"
        },{
          "url": "https://github.com/advisories/GHSA-9r2w-394v-53qc"
        },{
          "url": "https://github.com/npm/node-tar/security/advisories/GHSA-9r2w-394v-53qc"
        },{
          "url": "https://linux.oracle.com/cve/CVE-2021-37701.html"
        },{
          "url": "https://linux.oracle.com/errata/ELSA-2022-0350.html"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-37701"
        },{
          "url": "https://www.debian.org/security/2021/dsa-5008"
        },{
          "url": "https://www.npmjs.com/advisories/1779"
        },{
          "url": "https://www.npmjs.com/package/tar"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-37712",
      "category": "container_scanning",
      "message": "nodejs-tar: Insufficient symlink protection due to directory cache poisoning using symbolic links allowing arbitrary file creation and overwrite",
      "description": "The npm package \"tar\" (aka node-tar) before versions 4.4.18, 5.0.10, and 6.1.9 has an arbitrary file creation/overwrite and arbitrary code execution vulnerability. node-tar aims to guarantee that any file whose location would be modified by a symbolic link is not extracted. This is, in part, achieved by ensuring that extracted directories are not symlinks. Additionally, in order to prevent unnecessary stat calls to determine whether a given path is a directory, paths are cached when directories are created. This logic was insufficient when extracting tar files that contained both a directory and a symlink with names containing unicode values that normalized to the same value. Additionally, on Windows systems, long path portions would resolve to the same file system entities as their 8.3 \"short path\" counterparts. A specially crafted tar archive could thus include a directory with one form of the path, followed by a symbolic link with a different string that resolves to the same file system entity, followed by a file using the first form. By first creating a directory, and then replacing that directory with a symlink that had a different apparent name that resolved to the same entry in the filesystem, it was thus possible to bypass node-tar symlink checks on directories, essentially allowing an untrusted tar file to symlink into an arbitrary location and subsequently extracting arbitrary files into that location, thus allowing arbitrary file creation and overwrite. These issues were addressed in releases 4.4.18, 5.0.10 and 6.1.9. The v3 branch of node-tar has been deprecated and did not receive patches for these issues. If you are still using a v3 release we recommend you update to a more recent version of node-tar. If this is not possible, a workaround is available in the referenced GHSA-qq89-hq3f-393p.",
      "cve": "CVE-2021-37712",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade tar to 6.1.9, 5.0.10, 4.4.18",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "tar"
          },
          "version": "2.2.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-37712",
          "value": "CVE-2021-37712",
          "url": "https://avd.aquasec.com/nvd/cve-2021-37712"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-37712"
        },{
          "url": "https://cert-portal.siemens.com/productcert/pdf/ssa-389290.pdf"
        },{
          "url": "https://github.com/advisories/GHSA-qq89-hq3f-393p"
        },{
          "url": "https://github.com/npm/node-tar/security/advisories/GHSA-qq89-hq3f-393p"
        },{
          "url": "https://linux.oracle.com/cve/CVE-2021-37712.html"
        },{
          "url": "https://linux.oracle.com/errata/ELSA-2022-0350.html"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-37712"
        },{
          "url": "https://www.debian.org/security/2021/dsa-5008"
        },{
          "url": "https://www.npmjs.com/advisories/1780"
        },{
          "url": "https://www.npmjs.com/package/tar"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-37713",
      "category": "container_scanning",
      "message": "nodejs-tar: Arbitrary File Creation/Overwrite on Windows via insufficient relative path sanitization",
      "description": "The npm package \"tar\" (aka node-tar) before versions 4.4.18, 5.0.10, and 6.1.9 has an arbitrary file creation/overwrite and arbitrary code execution vulnerability. node-tar aims to guarantee that any file whose location would be outside of the extraction target directory is not extracted. This is, in part, accomplished by sanitizing absolute paths of entries within the archive, skipping archive entries that contain `..` path portions, and resolving the sanitized paths against the extraction target directory. This logic was insufficient on Windows systems when extracting tar files that contained a path that was not an absolute path, but specified a drive letter different from the extraction target, such as `C:some\\path`. If the drive letter does not match the extraction target, for example `D:\\extraction\\dir`, then the result of `path.resolve(extractionDirectory, entryPath)` would resolve against the current working directory on the `C:` drive, rather than the extraction target directory. Additionally, a `..` portion of the path could occur immediately after the drive letter, such as `C:../foo`, and was not properly sanitized by the logic that checked for `..` within the normalized and split portions of the path. This only affects users of `node-tar` on Windows systems. These issues were addressed in releases 4.4.18, 5.0.10 and 6.1.9. The v3 branch of node-tar has been deprecated and did not receive patches for these issues. If you are still using a v3 release we recommend you update to a more recent version of node-tar. There is no reasonable way to work around this issue without performing the same path normalization procedures that node-tar now does. Users are encouraged to upgrade to the latest patched versions of node-tar, rather than attempt to sanitize paths themselves.",
      "cve": "CVE-2021-37713",
      "severity": "High",
      "confidence": "Unknown",
      "solution": "Upgrade tar to 6.1.9, 5.0.10, 4.4.18",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "tar"
          },
          "version": "2.2.2"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-37713",
          "value": "CVE-2021-37713",
          "url": "https://avd.aquasec.com/nvd/cve-2021-37713"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-37713"
        },{
          "url": "https://cert-portal.siemens.com/productcert/pdf/ssa-389290.pdf"
        },{
          "url": "https://github.com/advisories/GHSA-5955-9wpr-37jh"
        },{
          "url": "https://github.com/npm/node-tar/security/advisories/GHSA-5955-9wpr-37jh"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-37713"
        },{
          "url": "https://www.npmjs.com/package/tar"
        },{
          "url": "https://www.oracle.com/security-alerts/cpuoct2021.html"
        }
      ]
    },
    {
      "id": "CVE-2021-23449",
      "category": "container_scanning",
      "message": "Prototype Pollution in vm2",
      "description": "This affects the package vm2 before 3.9.4 via a Prototype Pollution attack vector, which can lead to execution of arbitrary code on the host machine.",
      "cve": "CVE-2021-23449",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade vm2 to 3.9.4",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "vm2"
          },
          "version": "3.9.3"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-23449",
          "value": "CVE-2021-23449",
          "url": "https://avd.aquasec.com/nvd/cve-2021-23449"
        }
      ],
      "links": [{
          "url": "https://github.com/advisories/GHSA-rjf2-j2r6-q8gr"
        },{
          "url": "https://github.com/patriksimek/vm2/commit/b4f6e2bd2c4a1ef52fc4483d8e35f28bc4481886"
        },{
          "url": "https://github.com/patriksimek/vm2/issues/363"
        },{
          "url": "https://github.com/patriksimek/vm2/releases/tag/3.9.4"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-23449"
        },{
          "url": "https://security.netapp.com/advisory/ntap-20211029-0010/"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-VM2-1585918"
        }
      ]
    },
    {
      "id": "CVE-2021-23555",
      "category": "container_scanning",
      "message": "vm2: vulnerable to Sandbox Bypass",
      "description": "The package vm2 before 3.9.6 are vulnerable to Sandbox Bypass via direct access to host error objects generated by node internals during generation of a stacktraces, which can lead to execution of arbitrary code on the host machine.",
      "cve": "CVE-2021-23555",
      "severity": "Critical",
      "confidence": "Unknown",
      "solution": "Upgrade vm2 to 3.9.6",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "vm2"
          },
          "version": "3.9.3"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2021-23555",
          "value": "CVE-2021-23555",
          "url": "https://avd.aquasec.com/nvd/cve-2021-23555"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2021-23555"
        },{
          "url": "https://github.com/advisories/GHSA-6pw2-5hjv-9pf7"
        },{
          "url": "https://github.com/patriksimek/vm2/commit/532120d5cdec7da8225fc6242e154ebabc63fe4d"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-23555"
        },{
          "url": "https://security.snyk.io/vuln/SNYK-JS-VM2-2309905"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-VM2-2309905"
        }
      ]
    },
    {
      "id": "CVE-2020-7608",
      "category": "container_scanning",
      "message": "nodejs-yargs-parser: prototype pollution vulnerability",
      "description": "yargs-parser could be tricked into adding or modifying properties of Object.prototype using a \"__proto__\" payload.",
      "cve": "CVE-2020-7608",
      "severity": "Medium",
      "confidence": "Unknown",
      "solution": "Upgrade yargs-parser to 5.0.1, 13.1.2, 18.1.2, 15.0.1",
      "scanner": {
        "id": "trivy",
        "name": "trivy"
      },
      "location": {
        "dependency": {
          "package": {
            "name": "yargs-parser"
          },
          "version": "11.1.1"
        },
        "operating_system": "Unknown",
        "image": "Node.js"
      },
      "identifiers": [
        {
          "type": "cve",
          "name": "CVE-2020-7608",
          "value": "CVE-2020-7608",
          "url": "https://avd.aquasec.com/nvd/cve-2020-7608"
        }
      ],
      "links": [{
          "url": "https://access.redhat.com/security/cve/CVE-2020-7608"
        },{
          "url": "https://errata.almalinux.org/8/ALSA-2021-0548.html"
        },{
          "url": "https://github.com/advisories/GHSA-p9pc-299p-vxgp"
        },{
          "url": "https://github.com/yargs/yargs-parser/commit/63810ca1ae1a24b08293a4d971e70e058c7a41e2"
        },{
          "url": "https://linux.oracle.com/cve/CVE-2020-7608.html"
        },{
          "url": "https://linux.oracle.com/errata/ELSA-2021-0548.html"
        },{
          "url": "https://nvd.nist.gov/vuln/detail/CVE-2020-7608"
        },{
          "url": "https://snyk.io/vuln/SNYK-JS-YARGSPARSER-560381"
        },{
          "url": "https://www.npmjs.com/advisories/1500"
        }
      ]
    }
  ],
  "remediations": []
}
````