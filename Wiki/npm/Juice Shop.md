# Juice Shop

base64url  <3.0.0
Severity: moderate
Out-of-bounds Read in base64url - https://github.com/advisories/GHSA-rvg8-pwq2-xj7q
fix available via `npm audit fix --force`
Will install jsonwebtoken@8.5.1, which is a breaking change
node_modules/base64url
  jwa  <=1.1.5
  Depends on vulnerable versions of base64url
  node_modules/jwa
    jws  <=3.1.4
    Depends on vulnerable versions of base64url
    Depends on vulnerable versions of jwa
    node_modules/jws
      jsonwebtoken  <=4.2.2
      Depends on vulnerable versions of jws
      Depends on vulnerable versions of moment
      node_modules/express-jwt/node_modules/jsonwebtoken
      node_modules/jsonwebtoken
        express-jwt  <=5.3.3
        Depends on vulnerable versions of jsonwebtoken
        node_modules/express-jwt
<font color="coral"> Updated in Package.json </font>


dicer  *
Severity: high
Crash in HeaderParser in dicer - https://github.com/advisories/GHSA-wm7h-9275-46v2
No fix available
node_modules/dicer
  busboy  <=0.3.1
  Depends on vulnerable versions of dicer
  node_modules/busboy
    multer  <=2.0.0-rc.3
    Depends on vulnerable versions of busboy
    node_modules/multer

ecstatic  <4.1.3
Severity: moderate
Denial of Service in ecstatic - https://github.com/advisories/GHSA-jc84-3g44-wf2q
fix available via `npm audit fix --force`
Will install http-server@14.1.1, which is a breaking change
node_modules/ecstatic
  http-server  0.4.0 - 0.12.3
  Depends on vulnerable versions of ecstatic
  node_modules/http-server

express-jwt  <=5.3.3
Severity: critical
Authorization bypass in express-jwt - https://github.com/advisories/GHSA-6g6m-m6h5-w9gf
Depends on vulnerable versions of jsonwebtoken
fix available via `npm audit fix --force`
Will install express-jwt@7.7.5, which is a breaking change
node_modules/express-jwt

jsonwebtoken  <=4.2.2
Severity: critical
Verification Bypass in jsonwebtoken - https://github.com/advisories/GHSA-c7hr-j4mj-j2w6
Depends on vulnerable versions of jws
Depends on vulnerable versions of moment
fix available via `npm audit fix --force`
Will install jsonwebtoken@8.5.1, which is a breaking change
node_modules/express-jwt/node_modules/jsonwebtoken
node_modules/jsonwebtoken
  express-jwt  <=5.3.3
  Depends on vulnerable versions of jsonwebtoken
  node_modules/express-jwt

jws  <=3.1.4
Severity: high
Forgeable Public/Private Tokens in jws - https://github.com/advisories/GHSA-gjcw-v447-2w7q
Depends on vulnerable versions of base64url
Depends on vulnerable versions of jwa
fix available via `npm audit fix --force`
Will install jsonwebtoken@8.5.1, which is a breaking change
node_modules/jws
  jsonwebtoken  <=4.2.2
  Depends on vulnerable versions of jws
  Depends on vulnerable versions of moment
  node_modules/express-jwt/node_modules/jsonwebtoken
  node_modules/jsonwebtoken
    express-jwt  <=5.3.3
    Depends on vulnerable versions of jsonwebtoken
    node_modules/express-jwt

lodash  <=4.17.20
Severity: critical
Prototype Pollution in lodash - https://github.com/advisories/GHSA-jf85-cpcp-j695
Prototype Pollution in lodash - https://github.com/advisories/GHSA-fvqr-27wr-82fm
Regular Expression Denial of Service (ReDoS) in lodash - https://github.com/advisories/GHSA-29mw-wpgm-hmr9
Regular Expression Denial of Service (ReDoS) in lodash - https://github.com/advisories/GHSA-x5rq-j2xg-h7qm
Prototype Pollution in lodash - https://github.com/advisories/GHSA-p6mc-m468-83gw
fix available via `npm audit fix --force`
Will install sanitize-html@2.7.0, which is a breaking change
node_modules/sanitize-html/node_modules/lodash
  sanitize-html  <=2.3.1
  Depends on vulnerable versions of lodash
  node_modules/sanitize-html

marsdb  *
Severity: critical
Command Injection in marsdb - https://github.com/advisories/GHSA-5mrr-rgp6-x4gr
No fix available
node_modules/marsdb

minimist  <1.2.6
Severity: critical
Prototype Pollution in minimist - https://github.com/advisories/GHSA-xvch-5gv4-984h
fix available via `npm audit fix`
node_modules/bower-config/node_modules/minimist
  bower-config  >=1.4.2
  Depends on vulnerable versions of minimist
  node_modules/bower-config

moment  <=2.29.1
Severity: high
Regular Expression Denial of Service in moment - https://github.com/advisories/GHSA-446m-mv8f-q348
Regular Expression Denial of Service in moment - https://github.com/advisories/GHSA-87vv-r9j6-g5qv
Path Traversal: 'dir/../../filename' in moment.locale - https://github.com/advisories/GHSA-8hfj-j24r-96c4
fix available via `npm audit fix --force`
Will install jsonwebtoken@8.5.1, which is a breaking change
node_modules/express-jwt/node_modules/moment
  jsonwebtoken  <=4.2.2
  Depends on vulnerable versions of jws
  Depends on vulnerable versions of moment
  node_modules/express-jwt/node_modules/jsonwebtoken
  node_modules/jsonwebtoken
    express-jwt  <=5.3.3
    Depends on vulnerable versions of jsonwebtoken
    node_modules/express-jwt

nanoid  3.0.0 - 3.1.30
Severity: moderate
Exposure of Sensitive Information to an Unauthorized Actor in nanoid - https://github.com/advisories/GHSA-qrpm-p2h7-hrv2
fix available via `npm audit fix`
node_modules/nanoid
  mocha  8.2.0 - 9.1.4
  Depends on vulnerable versions of nanoid
  node_modules/mocha

notevil  *
Severity: moderate
Sandbox escape in notevil and argencoders-notevil - https://github.com/advisories/GHSA-8g4m-cjm2-96wq
No fix available
node_modules/notevil

sanitize-html  <=2.3.1
Severity: high
Improper Input Validation in sanitize-html - https://github.com/advisories/GHSA-mjxr-4v3x-q3m4
Cross-Site Scripting in sanitize-html - https://github.com/advisories/GHSA-3j7m-hmh3-9jmp
Cross-Site Scripting in sanitize-html - https://github.com/advisories/GHSA-xc6g-ggrc-qq4r
Improper Input Validation in sanitize-html - https://github.com/advisories/GHSA-rjqq-98f6-6j3r
Depends on vulnerable versions of lodash
fix available via `npm audit fix --force`
Will install sanitize-html@2.7.0, which is a breaking change
node_modules/sanitize-html

sqlite3  5.0.0 - 5.0.2
Severity: high
Denial-of-Service when binding invalid parameters in sqlite3 - https://github.com/advisories/GHSA-9qrh-qjmc-5w2p
Depends on vulnerable versions of node-gyp
fix available via `npm audit fix --force`
Will install sqlite3@5.0.8, which is outside the stated dependency range
node_modules/sqlite3

tar  <=4.4.17
Severity: high
Arbitrary File Creation/Overwrite via insufficient symlink protection due to directory cache poisoning using symbolic links - https://github.com/advisories/GHSA-qq89-hq3f-393p
Arbitrary File Creation/Overwrite via insufficient symlink protection due to directory cache poisoning using symbolic links - https://github.com/advisories/GHSA-9r2w-394v-53qc
Arbitrary File Creation/Overwrite due to insufficient absolute path sanitization - https://github.com/advisories/GHSA-3jfq-g458-7qm9
Arbitrary File Creation/Overwrite via insufficient symlink protection due to directory cache poisoning - https://github.com/advisories/GHSA-r628-mhmh-qjhw
fix available via `npm audit fix --force`
Will install sqlite3@5.0.8, which is outside the stated dependency range
node_modules/node-gyp/node_modules/tar
  node-gyp  <=3.8.0
  Depends on vulnerable versions of tar
  node_modules/node-gyp
    sqlite3  5.0.0 - 5.0.2
    Depends on vulnerable versions of node-gyp
    node_modules/sqlite3

vm2  <=3.9.5
Severity: critical
Sandbox bypass in vm2 - https://github.com/advisories/GHSA-6pw2-5hjv-9pf7
Prototype Pollution in vm2 - https://github.com/advisories/GHSA-rjf2-j2r6-q8gr
fix available via `npm audit fix --force`
Will install juicy-chat-bot@0.6.4, which is a breaking change
node_modules/vm2
  juicy-chat-bot  >=0.6.5
  Depends on vulnerable versions of vm2
  node_modules/juicy-chat-bot

yargs-parser  6.0.0 - 13.1.1
Severity: moderate
Prototype Pollution in yargs-parser - https://github.com/advisories/GHSA-p9pc-299p-vxgp
fix available via `npm audit fix --force`
Will install webdriver-manager@12.1.8, which is a breaking change
node_modules/webdriver-manager/node_modules/yargs-parser
  yargs  8.0.0-candidate.0 - 12.0.5
  Depends on vulnerable versions of yargs-parser
  node_modules/webdriver-manager/node_modules/yargs
    webdriver-manager  >=13.0.0-beta
    Depends on vulnerable versions of yargs
    node_modules/webdriver-manager