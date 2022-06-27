# Report sast-semgrep für die Juice Shop-Pipeline

````
Findings:

  

  .devcontainer.json

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         13┆ "postCreateCommand": "export NG_CLI_ANALYTICS=ci && npm i -g @angular/cli && npm install"

  
  

  .github/workflows/ci.yml

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         34┆ npm install --ignore-scripts

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

         36┆ npm install --ignore-scripts --legacy-peer-deps

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

         65┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

         88┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        128┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        193┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        225┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        252┆ run: npm install

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        282┆ npm install --production

  
  

  .github/workflows/lint-fixer.yml

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         19┆ npm install --ignore-scripts

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

         21┆ npm install --ignore-scripts --legacy-peer-deps

  
  

  .github/workflows/release.yml

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         38┆ npm install --production

  
  

  Dockerfile

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

          5┆ RUN npm install --production --unsafe-perm

  
  

  Dockerfile.arm

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

          5┆ RUN npm install --production --unsafe-perm

  
  

  Gruntfile.js

     ajinabraham.njsscan.crypto_node.node_md5

        MD5 is a a weak hash which is known to have collision. Use a strong hashing function.

        Details: https://sg.run/zvXk

  

         73┆ const md5 = crypto.createHash('md5')

          ⋮┆----------------------------------------

     javascript.lang.security.audit.detect-non-literal-fs-filename.detect-non-literal-fs-filename

        A variable is present in the filename argument of fs calls, this might allow an attacker to

        access anything on your system.

        Details: https://sg.run/8RNQ

  

         72┆ const buffer = fs.readFileSync('dist/' + file)

  
  

  README.md

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         89┆ 4. Run `npm install` (only has to be done before first start or when you change the source code)

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ npm ci

        108┆ > `libxmljs` bound to the OS and node.js version which `npm install` was

  
  

  data/datacreator.ts

     ajinabraham.njsscan.crypto_node.node_insecure_random_generator

        crypto.pseudoRandomBytes()/Math.random() is a cryptographically weak random number

        generator.

        Details: https://sg.run/1Zlk

  

        223┆ for (let i = 0; i < length; i++) { text += possible.charAt(Math.floor(Math.random() * possible.length)) }

          ⋮┆----------------------------------------

        241┆ quantity: product.quantity !== undefined ? product.quantity : Math.floor(Math.random() * 70 + 30),

          ⋮┆----------------------------------------

        289┆ product.price = product.price ?? Math.floor(Math.random() * 9 + 1)

          ⋮┆----------------------------------------

        667┆ eta: Math.floor((Math.random() * 5) + 1).toString(),

          ⋮┆----------------------------------------

     javascript.lang.security.audit.path-traversal.path-join-resolve-traversal.path-join-resolve-traversal

        Possible writing outside of the destination, make sure that the target path is nested in the

        intended destination

        Details: https://sg.run/OPqk

  

         41┆ const filePath = path.resolve('./data/static/' + file + '.yml')

  
  

  data/static/codefixes/adminSectionChallenge_3.ts

     javascript.lang.security.audit.code-string-concat.code-string-concat

        User controlled data in eval() or similar functions may result in Code Injection

        Details: https://sg.run/96Yk

  

          3┆  ... function(){var t=Array.prototype.slice.call(arguments),G=t.shift();return t.reverse().map(function(e,w){return String.fromCharCode(e-G-2-w)}).join('')})(55,167, ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

          ⋮┆----------------------------------------

          3┆  ... function(){var t=Array.prototype.slice.call(arguments),G=t.shift();return t.reverse().map(function(e,w){return String.fromCharCode(e-G-2-w)}).join('')})(55,167, ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  data/static/codefixes/dbSchemaChallenge_1.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

          5┆ models.sequelize.query("SELECT * FROM Products WHERE ((name LIKE '%"+criteria+"%' OR description LIKE '%"+criteria+"%') AND deletedAt IS NULL) ORDER BY name")

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

          5┆ models.sequelize.query("SELECT * FROM Products WHERE ((name LIKE '%"+criteria+"%' OR description LIKE '%"+criteria+"%') AND deletedAt IS NULL) ORDER BY name")

  
  

  data/static/codefixes/dbSchemaChallenge_2_correct.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

          5┆ models.sequelize.query(

          6┆     `SELECT * FROM Products WHERE ((name LIKE '%:criteria%' OR description LIKE '%:criteria%') AND deletedAt IS NULL) ORDER BY name`,

          7┆     { replacements: { criteria } }

          8┆   ).then(([products]: any) => {

  
  

  data/static/codefixes/dbSchemaChallenge_3.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

         11┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

         11┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

  
  

  data/static/codefixes/localXssChallenge_1.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

          6┆ this.searchValue = this.sanitizer.bypassSecurityTrustResourceUrl(queryParam)

  
  

  data/static/codefixes/localXssChallenge_3.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

          6┆ this.searchValue = this.sanitizer.bypassSecurityTrustScript(queryParam)

  
  

  data/static/codefixes/localXssChallenge_4.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

          6┆ this.searchValue = this.sanitizer.bypassSecurityTrustStyle(queryParam)

  
  

  data/static/codefixes/restfulXssChallenge_2.ts

     javascript.lang.correctness.no-replaceall.no-replaceall

        The string method replaceAll is not supported in all versions of javascript, and is not

        supported by older browser versions. Consider using replace() with a regex as the first

        argument instead like mystring.replace(/bad/g, "good") instead of mystring.replaceAll("bad",

        "good") (https://discourse.threejs.org/t/replaceall-is-not-a-function/14585)

        Details: https://sg.run/W8NE

  

         59┆ tableData[i].description = tableData[i].description.replaceAll('<', '&lt;').replaceAll('>', '&gt;')

          ⋮┆----------------------------------------

         59┆ tableData[i].description = tableData[i].description.replaceAll('<', '&lt;').replaceAll('>', '&gt;')

  
  

  data/static/codefixes/restfulXssChallenge_3.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         45┆ tableData[i].description = this.sanitizer.bypassSecurityTrustHtml(tableData[i].description)

  
  

  data/static/codefixes/restfulXssChallenge_4.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         59┆ tableData[i].description = this.sanitizer.bypassSecurityTrustScript(tableData[i].description)

  
  

  data/static/codefixes/unionSqlInjectionChallenge_1.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

          6┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

          6┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

  
  

  data/static/codefixes/unionSqlInjectionChallenge_2_correct.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

          5┆ models.sequelize.query(

          6┆     `SELECT * FROM Products WHERE ((name LIKE '%:criteria%' OR description LIKE '%:criteria%') AND deletedAt IS NULL) ORDER BY name`,

          7┆     { replacements: { criteria } }

          8┆   ).then(([products]: any) => {

  
  

  data/static/codefixes/unionSqlInjectionChallenge_3.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

         10┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

         10┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`)

  
  

  data/static/codefixes/xssBonusChallenge_2.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

          6┆ this.searchValue = this.sanitizer.bypassSecurityTrustResourceUrl(queryParam)

  
  

  data/static/users.yml

     generic.secrets.security.detected-generic-secret.detected-generic-secret

        Generic Secret detected

        Details: https://sg.run/l2o5

  

        150┆ totpSecret: IFTXE3SPOEYVURT2MRYGI52TKJ4HC3KH

  
  

  docker-compose.test.yml

     yaml.docker-compose.security.no-new-privileges.no-new-privileges

        Service 'app' allows for privilege escalation via setuid or setgid binaries. Add 'no-new-

        privileges:true' in 'security_opt' to prevent this.

        Details: https://sg.run/0n8q

  

          7┆ app:

          8┆   image: bkimminich/juice-shop:latest-amd64

          9┆   build: ./

          ⋮┆----------------------------------------

     yaml.docker-compose.security.writable-filesystem-service.writable-filesystem-service

        Service 'app' is running with a writable root filesystem. This may allow malicious

        applications to download and run additional payloads, or modify container files. If an

        application inside a container has to save something temporarily consider using a tmpfs. Add

        'read_only: true' to this service to prevent this.

        Details: https://sg.run/e4JE

  

          7┆ app:

          8┆   image: bkimminich/juice-shop:latest-amd64

          9┆   build: ./

  
  

  frontend/src/app/Services/security-question.service.spec.ts

     generic.secrets.security.detected-username-and-password-in-uri.detected-username-and-password-in-uri

        Username and password in URI detected

        Details: https://sg.run/8yA4

  

         42┆ const req = httpMock.expectOne('http://localhost:3000/rest/user/security-question?email=x@y.z')

  
  

  frontend/src/app/about/about.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         81┆ feedbacks[i].comment = this.sanitizer.bypassSecurityTrustHtml(feedbacks[i].comment)

  
  

  frontend/src/app/administration/administration.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         51┆ user.email = this.sanitizer.bypassSecurityTrustHtml(`<span class="${user.token ? 'confirmation' : 'error'}">${user.email}</span>`)

          ⋮┆----------------------------------------

         66┆ feedback.comment = this.sanitizer.bypassSecurityTrustHtml(feedback.comment)

  
  

  frontend/src/app/app.guard.spec.ts

     generic.secrets.security.detected-jwt-token.detected-jwt-token

        JWT token detected

        Details: https://sg.run/05N5

  

         40┆  ... eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c') ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  frontend/src/app/change-password/change-password.component.ts

     ajinabraham.njsscan.timing_attack_node.node_timing_attack

        String comparisons using '===', '!==', '!=' and '==' is vulnerable to timing attacks. More

        info: https://snyk.io/blog/node-js-timing-attack-ccc-ctf/

        Details: https://sg.run/9oj0

  

         81┆ if (password !== passwordRepeat) {

         82┆   return { notSame: true }

         83┆ }

  
  

  frontend/src/app/code-fixes/code-fixes.component.ts

     ajinabraham.njsscan.crypto_node.node_insecure_random_generator

        crypto.pseudoRandomBytes()/Math.random() is a cryptographically weak random number

        generator.

        Details: https://sg.run/1Zlk

  

         34┆ let randomRotation = Math.random() * 100

  
  

  frontend/src/app/data-export/data-export.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         45┆ this.captcha = this.sanitizer.bypassSecurityTrustHtml(data.image)

  
  

  frontend/src/app/forgot-password/forgot-password.component.ts

     ajinabraham.njsscan.timing_attack_node.node_timing_attack

        String comparisons using '===', '!==', '!=' and '==' is vulnerable to timing attacks. More

        info: https://snyk.io/blog/node-js-timing-attack-ccc-ctf/

        Details: https://sg.run/9oj0

  

        119┆ if (password !== passwordRepeat) {

        120┆   return { notSame: true }

        121┆ }

  
  

  frontend/src/app/last-login-ip/last-login-ip.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         36┆ this.lastLoginIp = this.sanitizer.bypassSecurityTrustHtml(`<small>${payload.data.lastLoginIp}</small>`)

  
  

  frontend/src/app/navbar/navbar.component.html

     python.flask.security.xss.audit.template-unquoted-attribute-var.template-unquoted-attribute-var

        Detected a unquoted template variable as an attribute. If unquoted, a malicious actor could

        inject custom JavaScript handlers. To fix this, add quotes around the template expression,

        like this: "{{ expr }}".

        Details: https://sg.run/0Qp5

  

         ▶▶┆ Autofix ▶ s/{{(.*?)}}/"{{\1}}"/g

         16┆ <img [src]="logoSrc" class="logo" alt={{applicationName}}>

  
  

  frontend/src/app/navbar/navbar.component.ts

     javascript.browser.security.open-redirect.js-open-redirect

        Possible open redirect

        Details: https://sg.run/3xRe

  

        196┆ window.location.replace(environment.hostServer + '/profile')

          ⋮┆----------------------------------------

        200┆ window.location.replace(environment.hostServer + '/dataerasure')

  
  

  frontend/src/app/product-details/product-details.component.html

     python.flask.security.xss.audit.template-unquoted-attribute-var.template-unquoted-attribute-var

        Detected a unquoted template variable as an attribute. If unquoted, a malicious actor could

        inject custom JavaScript handlers. To fix this, add quotes around the template expression,

        like this: "{{ expr }}".

        Details: https://sg.run/0Qp5

  

         ▶▶┆ Autofix ▶ s/{{(.*?)}}/"{{\1}}"/g

         11┆ <img class="img-thumbnail" [src]="'assets/public/images/products/'+data.productData.image" alt={{data.productData.name}}>

  
  

  frontend/src/app/purchase-basket/purchase-basket.component.html

     python.flask.security.xss.audit.template-unquoted-attribute-var.template-unquoted-attribute-var

        Detected a unquoted template variable as an attribute. If unquoted, a malicious actor could

        inject custom JavaScript handlers. To fix this, add quotes around the template expression,

        like this: "{{ expr }}".

        Details: https://sg.run/0Qp5

  

         ▶▶┆ Autofix ▶ s/{{(.*?)}}/"{{\1}}"/g

         15┆ <img [src]="'assets/public/images/products/'+element.image" alt={{element.name}}

  
  

  frontend/src/app/register/register.component.ts

     ajinabraham.njsscan.timing_attack_node.node_timing_attack

        String comparisons using '===', '!==', '!=' and '==' is vulnerable to timing attacks. More

        info: https://snyk.io/blog/node-js-timing-attack-ccc-ctf/

        Details: https://sg.run/9oj0

  

         94┆ if (password !== passwordRepeat) {

         95┆   return { notSame: true }

         96┆ }

  
  

  frontend/src/app/score-board/score-board.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

        182┆ challenge.description = this.sanitizer.bypassSecurityTrustHtml(challenge.description as string)

  
  

  frontend/src/app/search-result/search-result.component.html

     python.flask.security.xss.audit.template-unquoted-attribute-var.template-unquoted-attribute-var

        Detected a unquoted template variable as an attribute. If unquoted, a malicious actor could

        inject custom JavaScript handlers. To fix this, add quotes around the template expression,

        like this: "{{ expr }}".

        Details: https://sg.run/0Qp5

  

         ▶▶┆ Autofix ▶ s/{{(.*?)}}/"{{\1}}"/g

         30┆ <img mat-card-image [src]="'assets/public/images/products/'+item.image" alt={{item.name}}

  
  

  frontend/src/app/search-result/search-result.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

        126┆ tableData[i].description = this.sanitizer.bypassSecurityTrustHtml(tableData[i].description) // vuln-code-snippet vuln-line restfulXssChallenge

          ⋮┆----------------------------------------

        152┆ this.searchValue = this.sanitizer.bypassSecurityTrustHtml(queryParam) // vuln-code-snippet vuln-line localXssChallenge xssBonusChallenge

  
  

  frontend/src/app/sidenav/sidenav.component.ts

     javascript.browser.security.open-redirect.js-open-redirect

        Possible open redirect

        Details: https://sg.run/3xRe

  

         87┆ window.location.replace(environment.hostServer + '/profile')

          ⋮┆----------------------------------------

         91┆ window.location.replace(environment.hostServer + '/dataerasure')

  
  

  frontend/src/app/track-result/track-result.component.ts

     typescript.angular.security.audit.angular-domsanitizer.angular-bypasssecuritytrust

        Bypassing the built-in sanitization could expose the application to cross-site scripting

        (XSS).

        Details: https://sg.run/KWxP

  

         42┆ this.results.orderNo = this.sanitizer.bypassSecurityTrustHtml(`<code>${results.data[0].orderId}</code>`)

  
  

  frontend/src/hacking-instructor/helpers/helpers.ts

     javascript.lang.security.audit.prototype-pollution.prototype-pollution-loop.prototype-pollution-loop

        Possibility of prototype polluting function detected. By adding or modifying attributes of

        an object prototype, it is possible to create attributes that exist on every object, or

        replace critical attributes with malicious ones. This can be problematic if the software

        depends on existence or non-existence of certain attributes, or uses pre-defined attributes

        of object prototype (such as hasOwnProperty, toString or valueOf). Possible mitigations

        might be: freezing the object prototype, using an object without prototypes (via

        Object.create(null) ), blocking modifications of attributes that resolve to object

        prototype, using Map instead of object.

        Details: https://sg.run/w1DB

  

         36┆ replacementValue = replacementValue[property]

  
  

  frontend/src/hacking-instructor/index.ts

     javascript.browser.security.insecure-document-method.insecure-document-method

        User controlled data in methods like `innerHTML`, `outerHTML` or `document.write` is an

        anti-pattern that can lead to XSS vulnerabilities

        Details: https://sg.run/LwA9

  

        107┆ textBox.innerHTML = snarkdown(hint.text)

          ⋮┆----------------------------------------

     typescript.react.security.audit.react-unsanitized-property.react-unsanitized-property

        User controlled data in a `textBox` is an anti-pattern that can lead to XSS vulnerabilities

        Details: https://sg.run/70Zv

  

        107┆ textBox.innerHTML = snarkdown(hint.text)

  
  

  ftp/package.json.bak

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

        130┆ "preupdate-webdriver": "npm install",

  
  

  lib/insecurity.ts

     ajinabraham.njsscan.crypto_node.node_insecure_random_generator

        crypto.pseudoRandomBytes()/Math.random() is a cryptographically weak random number

        generator.

        Details: https://sg.run/1Zlk

  

         54┆ exports.denyAll = () => expressJwt({ secret: '' + Math.random() })

          ⋮┆----------------------------------------

     ajinabraham.njsscan.crypto_node.node_md5

        MD5 is a a weak hash which is known to have collision. Use a strong hashing function.

        Details: https://sg.run/zvXk

  

         42┆ exports.hash = (data: string) => crypto.createHash('md5').update(data).digest('hex')

          ⋮┆----------------------------------------

     ajinabraham.njsscan.jwt_hardcoded.hardcoded_jwt_secret

        Hardcoded JWT secret was found. Store it properly in an environment variable.

        Details: https://sg.run/Do3v

  

         12┆ const jwt = require('jsonwebtoken')

         13┆ const jws = require('jws')

         14┆ const sanitizeHtml = require('sanitize-html')

         15┆ const sanitizeFilename = require('sanitize-filename')

         16┆ const z85 = require('z85')

         17┆ const utils = require('./utils')

         18┆ const fs = require('fs')

         19┆

         20┆ const publicKey = fs.readFileSync('encryptionkeys/jwt.pub', 'utf8')

         21┆ module.exports.publicKey = publicKey

           [hid 34 additional lines, adjust with --max-lines-per-finding]

     ajinabraham.njsscan.jwt_not_revoked.jwt_not_revoked

        No token revoking configured for `express-jwt`. A leaked token could still be used and

        unable to be revoked. Consider using function as the `isRevoked` option.

        Details: https://sg.run/0Q3r

  

         53┆ exports.isAuthorized = () => expressJwt({ secret: publicKey })

          ⋮┆----------------------------------------

         54┆ exports.denyAll = () => expressJwt({ secret: '' + Math.random() })

          ⋮┆----------------------------------------

         53┆ exports.isAuthorized = () => expressJwt({ secret: publicKey })

          ⋮┆----------------------------------------

         54┆ exports.denyAll = () => expressJwt({ secret: '' + Math.random() })

          ⋮┆----------------------------------------

     javascript.jsonwebtoken.security.audit.jwt-exposed-data.jwt-exposed-data

        The object is passed strictly to jsonwebtoken.sign(...) Make sure that sensitive information

        is not exposed through JWT token payload.

        Details: https://sg.run/5Qkj

  

         55┆ exports.authorize = (user = {}) => jwt.sign(user, privateKey, { expiresInMinutes: 60 * 5, algorithm: 'RS256' })

          ⋮┆----------------------------------------

     javascript.jsonwebtoken.security.jwt-hardcode.hardcoded-jwt-secret

        Hardcoded JWT secret or private key is used. This is a Insufficiently Protected Credentials

        weakness: https://cwe.mitre.org/data/definitions/522.html Consider using an appropriate

        security mechanism to protect the credentials (e.g. keeping secrets in environment

        variables: process.env.SECRET)

        Details: https://sg.run/4xN9

  

         55┆ exports.authorize = (user = {}) => jwt.sign(user, privateKey, { expiresInMinutes: 60 * 5, algorithm: 'RS256' })

          ⋮┆----------------------------------------

         55┆ exports.authorize = (user = {}) => jwt.sign(user, privateKey, { expiresInMinutes: 60 * 5, algorithm: 'RS256' })

  
  

  lib/startup/validateChatBot.ts

     javascript.lang.security.audit.code-string-concat.code-string-concat

        User controlled data in eval() or similar functions may result in Code Injection

        Details: https://sg.run/96Yk

  

         37┆  ... function')} action and handler ${colors.italic(handler)} is missing for intent ${colors.italic(intent)} (${colors.red('NOT OK')})`) ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  lib/startup/validateConfig.ts

     javascript.lang.security.audit.code-string-concat.code-string-concat

        User controlled data in eval() or similar functions may result in Code Injection

        Details: https://sg.run/96Yk

  

        109┆  ... ({ name }) => `${colors.italic(name)}`).join(' and ')} but can only be used for one challenge (${colors.red('NOT OK')})`) ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

          ⋮┆----------------------------------------

        160┆  ... ({ name }) => `${colors.italic(name)}`).join(' and ')} but can only be used for one challenge (${colors.red('NOT OK')})`) ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  lib/startup/validateDependencies.ts

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         12┆ console.error('Please run "npm install" before starting the application!')

  
  

  lib/startup/validatePreconditions.ts

     javascript.lang.security.audit.path-traversal.path-join-resolve-traversal.path-join-resolve-traversal

        Possible writing outside of the destination, make sure that the target path is nested in the

        intended destination

        Details: https://sg.run/OPqk

  

         95┆ return access(path.resolve(pathRelativeToProjectRoot)).then(() => {

  
  

  package.json

     generic.ci.security.use-frozen-lockfile.use-frozen-lockfile-npm

        To ensure reproducable and deterministic builds, use `npm ci` rather than `npm install` in

        scripts. This will use the lockfile rather than updating it.

        Details: https://sg.run/Ry3v

  

         ▶▶┆ Autofix ▶ npm ci

         55┆ "postinstall": "cd frontend && npm install --legacy-peer-deps && cd .. && npm run build:frontend && (npm run --silent build:server || cd .)",

  
  

  routes/address.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         18┆ const address = await AddressModel.findOne({ where: { id: req.params.id, UserId: req.body.UserId } })

  
  

  routes/basket.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         16┆ const id = req.params.id

         17┆ BasketModel.findOne({ where: { id }, include: [{ model: ProductModel, paranoid: false, as: 'Products' }] })

         18┆   .then((basket: BasketModel | null) => {

         19┆     /* jshint eqeqeq:false */

         20┆     utils.solveIf(challenges.basketAccessChallenge, () => {

         21┆       const user = security.authenticatedUsers.from(req)

         22┆       return user && id && id !== 'undefined' && id !== 'null' && id !== 'NaN' && user.bid && user.bid != id // eslint-disable-line eqeqeq

         23┆     })

         24┆     if (basket?.Products && basket.Products.length > 0) {

         25┆       for (let i = 0; i < basket.Products.length; i++) {

           [hid 8 additional lines, adjust with --max-lines-per-finding]

         17┆ BasketModel.findOne({ where: { id }, include: [{ model: ProductModel, paranoid: false, as: 'Products' }] })

  
  

  routes/basketItems.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         66┆ BasketItemModel.findOne({ where: { id: req.params.id } }).then((item: BasketItemModel | null) => {

  
  

  routes/captcha.ts

     ajinabraham.njsscan.crypto_node.node_insecure_random_generator

        crypto.pseudoRandomBytes()/Math.random() is a cryptographically weak random number

        generator.

        Details: https://sg.run/1Zlk

  

         15┆ const firstTerm = Math.floor((Math.random() * 10) + 1)

          ⋮┆----------------------------------------

         16┆ const secondTerm = Math.floor((Math.random() * 10) + 1)

          ⋮┆----------------------------------------

         17┆ const thirdTerm = Math.floor((Math.random() * 10) + 1)

          ⋮┆----------------------------------------

         19┆ const firstOperator = operators[Math.floor((Math.random() * 3))]

          ⋮┆----------------------------------------

         20┆ const secondOperator = operators[Math.floor((Math.random() * 3))]

          ⋮┆----------------------------------------

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         37┆ CaptchaModel.findOne({ where: { captchaId: req.body.captchaId } }).then((captcha: Captcha | null) => {

          ⋮┆----------------------------------------

     javascript.browser.security.eval-detected.eval-detected

        Detected the use of eval(). eval() can be dangerous if used to evaluate dynamic content. If

        this content can be input from outside the program, this may be a code injection

        vulnerability. Ensure evaluated content is not definable by external sources.

        Details: https://sg.run/7ope

  

         23┆ const answer = eval(expression).toString() // eslint-disable-line no-eval

          ⋮┆----------------------------------------

     javascript.lang.security.detect-eval-with-expression.detect-eval-with-expression

        Detected eval(variable), which could allow a malicious actor to run arbitrary code.

        Details: https://sg.run/6nwK

  

         23┆ const answer = eval(expression).toString() // eslint-disable-line no-eval

  
  

  routes/countryMapping.ts

     javascript.express.security.audit.xss.direct-response-write.direct-response-write

        Detected directly writing to a Response object. This bypasses any HTML escaping and may

        expose your app to a cross-site scripting (XSS) vulnerability. Instead, use 'resp.render()'

        to render safely escaped HTML.

        Details: https://sg.run/vzGl

  

         ▶▶┆ Autofix ▶ res.render(countryMapping)

         16┆ res.send(countryMapping)

  
  

  routes/dataErasure.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         24┆ const email = loggedInUser.data.email

         25┆

         26┆ try {

         27┆   const answer = await SecurityAnswerModel.findOne({

         28┆     include: [{

         29┆       model: UserModel,

         30┆       where: { email }

         31┆     }]

         32┆   })

         33┆   if (!answer) {

           [hid 11 additional lines, adjust with --max-lines-per-finding]

         27┆ const answer = await SecurityAnswerModel.findOne({

         28┆   include: [{

         29┆     model: UserModel,

         30┆     where: { email }

         31┆   }]

         32┆ })

          ⋮┆----------------------------------------

     javascript.express.security.audit.xss.direct-response-write.direct-response-write

        Detected directly writing to a Response object. This bypasses any HTML escaping and may

        expose your app to a cross-site scripting (XSS) vulnerability. Instead, use 'resp.render()'

        to render safely escaped HTML.

        Details: https://sg.run/vzGl

  

         ▶▶┆ Autofix ▶ res.render(sendlfrResponse)

         79┆ res.send(sendlfrResponse)

  
  

  routes/delivery.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         34┆ const method = await DeliveryModel.findOne({ where: { id: req.params.id } })

  
  

  routes/deluxe.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         18┆ const user = await UserModel.findOne({ where: { id: req.body.UserId, role: security.roles.customer } })

          ⋮┆----------------------------------------

         24┆ const wallet = await WalletModel.findOne({ where: { UserId: req.body.UserId } })

          ⋮┆----------------------------------------

         34┆ const card = await CardModel.findOne({ where: { id: req.body.paymentId, UserId: req.body.UserId } })

  
  

  routes/fileUpload.ts

     javascript.lang.security.audit.path-traversal.path-join-resolve-traversal.path-join-resolve-traversal

        Possible writing outside of the destination, make sure that the target path is nested in the

        intended destination

        Details: https://sg.run/OPqk

  

         47┆ const fileName = entry.path

         48┆ const absolutePath = path.resolve('uploads/complaints/' + fileName)

  
  

  routes/likeProductReviews.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         16┆ const id = req.body.id

         17┆ const user = security.authenticatedUsers.from(req)

         18┆ db.reviews.findOne({ _id: id }).then((review: Review) => {

         19┆   if (!review) {

         20┆     res.status(404).json({ error: 'Not found' })

         21┆   } else {

         22┆     const likedBy = review.likedBy

         23┆     if (!likedBy.includes(user.data.email)) {

         24┆       db.reviews.update(

         25┆         { _id: id },

           [hid 38 additional lines, adjust with --max-lines-per-finding]

  
  

  routes/login.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

         35┆ models.sequelize.query(`SELECT * FROM Users WHERE email = '${req.body.email || ''}' AND password = '${security.hash(req.body.password || '')}' AND deletedAt IS  ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

         35┆ models.sequelize.query(`SELECT * FROM Users WHERE email = '${req.body.email || ''}' AND password = '${security.hash(req.body.password || '')}' AND deletedAt IS  ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  routes/order.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         35┆ const id = req.params.id

         36┆ BasketModel.findOne({ where: { id }, include: [{ model: ProductModel, paranoid: false, as: 'Products' }] })

         37┆   .then(async (basket: BasketModel | null) => {

         38┆     if (basket) {

         39┆       const customer = security.authenticatedUsers.from(req)

         40┆       const email = customer ? customer.data ? customer.data.email : '' : ''

         41┆       const orderId = security.hash(email).slice(0, 4) + '-' + utils.randomHexString(16)

         42┆       const pdfFile = `order_${orderId}.pdf`

         43┆       const doc = new PDFDocument()

         44┆       const date = new Date().toJSON().slice(0, 10)

           [hid 130 additional lines, adjust with --max-lines-per-finding]

         36┆ BasketModel.findOne({ where: { id }, include: [{ model: ProductModel, paranoid: false, as: 'Products' }] })

          ⋮┆----------------------------------------

         71┆ QuantityModel.findOne({ where: { ProductId: BasketItem.ProductId } }).then((product: any) => {

          ⋮┆----------------------------------------

        117┆ const deliveryMethodFromModel = await DeliveryModel.findOne({ where: { id: req.body.orderDetails.deliveryMethodId } })

          ⋮┆----------------------------------------

        140┆ const wallet = await WalletModel.findOne({ where: { UserId: req.body.UserId } })

          ⋮┆----------------------------------------

     javascript.lang.security.audit.detect-non-literal-fs-filename.detect-non-literal-fs-filename

        A variable is present in the filename argument of fs calls, this might allow an attacker to

        access anything on your system.

        Details: https://sg.run/8RNQ

  

         45┆ const fileWriter = doc.pipe(fs.createWriteStream(path.join('ftp/', pdfFile)))

  
  

  routes/payment.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         41┆ const card = await CardModel.findOne({ where: { id: req.params.id, UserId: req.body.UserId } })

  
  

  routes/profileImageUrlUpload.ts

     ajinabraham.njsscan.ssrf_node.node_ssrf

        User controlled URL in http client libraries can result in Server Side Request Forgery

        (SSRF).

        Details: https://sg.run/J90d

  

         18┆ const url = req.body.imageUrl

         19┆ if (url.match(/(.)*solve\/challenges\/server-side(.)*/) !== null) req.app.locals.abused_ssrf_bug = true

         20┆ const loggedInUser = security.authenticatedUsers.get(req.cookies.token)

         21┆ if (loggedInUser) {

         22┆   const imageRequest = request

         23┆     .get(url)

         24┆     .on('error', function (err: unknown) {

         25┆       UserModel.findByPk(loggedInUser.data.id).then(async (user: UserModel | null) => { return await user?.update({ profileImage: url }) }).catch((error: Error) ... [0m

         26┆       logger.warn(`Error retrieving user profile image: ${utils.getErrorMessage(err)}; using image link directly`)

         27┆     })

          [shortened a long line from output, adjust with --max-chars-per-line]

           [hid 10 additional lines, adjust with --max-lines-per-finding]

         20┆ const loggedInUser = security.authenticatedUsers.get(req.cookies.token)

  
  

  routes/recycles.ts

     javascript.express.security.audit.xss.direct-response-write.direct-response-write

        Detected directly writing to a Response object. This bypasses any HTML escaping and may

        expose your app to a cross-site scripting (XSS) vulnerability. Instead, use 'resp.render()'

        to render safely escaped HTML.

        Details: https://sg.run/vzGl

  

         ▶▶┆ Autofix ▶ res.render(utils.queryResultToJson(Recycle))

         17┆ return res.send(utils.queryResultToJson(Recycle))

          ⋮┆----------------------------------------

         ▶▶┆ Autofix ▶ res.render(utils.queryResultToJson(errMsg))

         25┆ return res.send(utils.queryResultToJson(errMsg))

  
  

  routes/redirect.ts

     javascript.express.security.audit.possible-user-input-redirect.unknown-value-in-redirect

        It looks like 'toUrl' is read from user input and it is used to as a redirect. Ensure

        'toUrl' is not externally controlled, otherwise this is an open redirect.

        Details: https://sg.run/OPv2

  

         18┆ res.redirect(toUrl as string)

  
  

  routes/resetPassword.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         19┆ const email = body.email

         20┆ const answer = body.answer

         21┆ const newPassword = body.new

         22┆ const repeatPassword = body.repeat

         23┆ if (!email || !answer) {

         24┆   next(new Error('Blocked illegal activity by ' + connection.remoteAddress))

         25┆ } else if (!newPassword || newPassword === 'undefined') {

         26┆   res.status(401).send(res.__('Password cannot be empty.'))

         27┆ } else if (newPassword !== repeatPassword) {

         28┆   res.status(401).send(res.__('New and repeated password do not match.'))

           [hid 25 additional lines, adjust with --max-lines-per-finding]

         30┆ SecurityAnswerModel.findOne({

         31┆   include: [{

         32┆     model: UserModel,

         33┆     where: { email }

         34┆   }]

         35┆ }).then((data: SecurityAnswerModel | null) => {

  
  

  routes/search.ts

     javascript.lang.security.audit.non-constant-sql-query.non-constant-sql-query

        Non-constant SQL query detected. Ensure this is not controlled by external data, otherwise

        this is a SQL injection.

        Details: https://sg.run/jRKP

  

         22┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`) //  ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

          ⋮┆----------------------------------------

     javascript.sequelize.security.audit.sequelize-raw-query.sequelize-raw-query

        Avoiding SQL string concatenation: untrusted input concatenated with raw SQL query can

        result in SQL Injection. Data replacement or data binding should be used. See

        https://sequelize.org/master/manual/raw-queries.html

        Details: https://sg.run/GeG6

  

         22┆ models.sequelize.query(`SELECT * FROM Products WHERE ((name LIKE '%${criteria}%' OR description LIKE '%${criteria}%') AND deletedAt IS NULL) ORDER BY name`) //  ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  routes/securityQuestion.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         13┆ const email = query.email

         14┆ SecurityAnswerModel.findOne({

         15┆   include: [{

         16┆     model: UserModel,

         17┆     where: { email: email?.toString() }

         18┆   }]

         19┆ }).then((answer: SecurityAnswerModel | null) => {

         20┆   if (answer) {

         21┆     SecurityQuestionModel.findByPk(answer.SecurityQuestionId).then((question: SecurityQuestionModel | null) => {

         22┆       res.json({ question })

           [hid 9 additional lines, adjust with --max-lines-per-finding]

         14┆ SecurityAnswerModel.findOne({

         15┆   include: [{

         16┆     model: UserModel,

         17┆     where: { email: email?.toString() }

         18┆   }]

         19┆ }).then((answer: SecurityAnswerModel | null) => {

  
  

  routes/showProductReviews.ts

     ajinabraham.njsscan.nosql_injection.node_nosqli_js_injection

        Untrusted user input in MongoDB $where operator can result in NoSQL JavaScript Injection.

        Details: https://sg.run/N4XL

  

         29┆ const id = utils.disableOnContainerEnv() ? Number(req.params.id) : req.params.id

         30┆

         31┆ // Measure how long the query takes, to check if there was a nosql dos attack

         32┆ const t0 = new Date().getTime()

         33┆ db.reviews.find({ $where: 'this.product == ' + id }).then((reviews: Review[]) => {

         34┆   const t1 = new Date().getTime()

         35┆   utils.solveIf(challenges.noSqlCommandChallenge, () => { return (t1 - t0) > 2000 })

         36┆   const user = security.authenticatedUsers.from(req)

         37┆   for (let i = 0; i < reviews.length; i++) {

         38┆     if (user === undefined || reviews[i].likedBy.includes(user.data.email)) {

           [hid 7 additional lines, adjust with --max-lines-per-finding]

  
  

  routes/trackOrder.ts

     ajinabraham.njsscan.nosql_injection.node_nosqli_js_injection

        Untrusted user input in MongoDB $where operator can result in NoSQL JavaScript Injection.

        Details: https://sg.run/N4XL

  

         14┆ const id = utils.disableOnContainerEnv() ? String(req.params.id).replace(/[^\w-]+/g, '') : req.params.id

         15┆

         16┆ utils.solveIf(challenges.reflectedXssChallenge, () => { return utils.contains(id, '<iframe src="javascript:alert(`xss`)">') })

         17┆ db.orders.find({ $where: `this.orderId === '${id}'` }).then((order: any) => {

         18┆   const result = utils.queryResultToJson(order)

         19┆   utils.solveIf(challenges.noSqlOrdersChallenge, () => { return result.data.length > 1 })

         20┆   if (result.data[0] === undefined) {

         21┆     result.data[0] = { orderId: id }

         22┆   }

         23┆   res.json(result)

           [hid 3 additional lines, adjust with --max-lines-per-finding]

  
  

  routes/userProfile.ts

     javascript.browser.security.eval-detected.eval-detected

        Detected the use of eval(). eval() can be dangerous if used to evaluate dynamic content. If

        this content can be input from outside the program, this may be a code injection

        vulnerability. Ensure evaluated content is not definable by external sources.

        Details: https://sg.run/7ope

  

         35┆ username = eval(code) // eslint-disable-line no-eval

          ⋮┆----------------------------------------

     javascript.express.security.audit.xss.direct-response-write.direct-response-write

        Detected directly writing to a Response object. This bypasses any HTML escaping and may

        expose your app to a cross-site scripting (XSS) vulnerability. Instead, use 'resp.render()'

        to render safely escaped HTML.

        Details: https://sg.run/vzGl

  

         ▶▶┆ Autofix ▶ res.render(fn(user))

         63┆ res.send(fn(user))

          ⋮┆----------------------------------------

     javascript.lang.security.audit.code-string-concat.code-string-concat

        User controlled data in eval() or similar functions may result in Code Injection

        Details: https://sg.run/96Yk

  

         56┆ const CSP = `img-src 'self' ${user?.profileImage}; script-src 'self' 'unsafe-eval' https://code.getmdl.io http://ajax.googleapis.com`

          ⋮┆----------------------------------------

     javascript.lang.security.detect-eval-with-expression.detect-eval-with-expression

        Detected eval(variable), which could allow a malicious actor to run arbitrary code.

        Details: https://sg.run/6nwK

  

         35┆ username = eval(code) // eslint-disable-line no-eval

  
  

  routes/verify.ts

     ajinabraham.njsscan.logic_bypass.node_logic_bypass

        User controlled data is used for application business logic decision making. This expose

        protected data or functionality.

        Details: https://sg.run/XB3N

  

         50┆ utils.solveIf(challenges.passwordRepeatChallenge, () => { return req.body && req.body.passwordRepeat !== req.body.password })

  
  

  routes/videoHandler.ts

     javascript.express.security.audit.xss.direct-response-write.direct-response-write

        Detected directly writing to a Response object. This bypasses any HTML escaping and may

        expose your app to a cross-site scripting (XSS) vulnerability. Instead, use 'resp.render()'

        to render safely escaped HTML.

        Details: https://sg.run/vzGl

  

         ▶▶┆ Autofix ▶ res.render(compiledTemplate)

         69┆ res.send(compiledTemplate)

          ⋮┆----------------------------------------

     javascript.lang.security.audit.unknown-value-with-script-tag.unknown-value-with-script-tag

        Cannot determine what 'subs' is and it is used with a '<script>' tag. This could be

        susceptible to cross-site scripting (XSS). Ensure 'subs' is not externally controlled, or

        sanitize this data.

        Details: https://sg.run/1Zy1

  

         68┆  ... compiledTemplate.replace('<script id="subtitle"></script>', '<script id="subtitle" type="text/vtt" data-label="English" data-lang="en">' + subs + '</script>') ... [0m

          [shortened a long line from output, adjust with --max-chars-per-line]

  
  

  routes/vulnCodeFixes.ts

     ajinabraham.njsscan.eval_yaml_deserialize.yaml_deserialize

        User controlled data in 'yaml.load()' function can result in Remote Code Injection.

        Details: https://sg.run/Do0v

  

         82┆ const codingChallengeInfos = yaml.load(fs.readFileSync('./data/static/codefixes/' + key + '.info.yml', 'utf8'))

          ⋮┆----------------------------------------

     javascript.lang.security.audit.detect-non-literal-fs-filename.detect-non-literal-fs-filename

        A variable is present in the filename argument of fs calls, this might allow an attacker to

        access anything on your system.

        Details: https://sg.run/8RNQ

  

         30┆ const fix = fs.readFileSync(`${FixesDir}/${file}`).toString()

          ⋮┆----------------------------------------

         81┆ if (fs.existsSync('./data/static/codefixes/' + key + '.info.yml')) {

          ⋮┆----------------------------------------

         82┆ const codingChallengeInfos = yaml.load(fs.readFileSync('./data/static/codefixes/' + key + '.info.yml', 'utf8'))

  
  

  routes/vulnCodeSnippet.ts

     javascript.lang.security.audit.detect-non-literal-regexp.detect-non-literal-regexp

        RegExp() called with a variable, this might allow an attacker to DOS your application with a

        long-running regular expression.

        Details: https://sg.run/gr65

  

        103┆ const match = new RegExp(`vuln-code-snippet start.*${challenge.key}`)

          ⋮┆----------------------------------------

        122┆ if (new RegExp(`vuln-code-snippet vuln-line.*${challenge.key}`).exec(lines[i]) != null) {

          ⋮┆----------------------------------------

        124┆ } else if (new RegExp(`vuln-code-snippet neutral-line.*${challenge.key}`).exec(lines[i]) != null) {

          ⋮┆----------------------------------------

     javascript.lang.security.audit.path-traversal.path-join-resolve-traversal.path-join-resolve-traversal

        Possible writing outside of the destination, make sure that the target path is nested in the

        intended destination

        Details: https://sg.run/OPqk

  

         32┆ const moreMatches = await fileSniff(files.map(file => path.resolve(currPath, file)), match)

  
  

  routes/wallet.ts

     ajinabraham.njsscan.nosql_find_injection.node_nosqli_injection

        Untrusted user input in findOne() function can result in NoSQL Injection.

        Details: https://sg.run/b7EP

  

         12┆ const wallet = await WalletModel.findOne({ where: { UserId: req.body.UserId } })

          ⋮┆----------------------------------------

         23┆ const cardId = req.body.paymentId

         24┆ const card = cardId ? await CardModel.findOne({ where: { id: cardId, UserId: req.body.UserId } }) : null

          ⋮┆----------------------------------------

         24┆ const card = cardId ? await CardModel.findOne({ where: { id: cardId, UserId: req.body.UserId } }) : null

  
  

  rsn/rsnUtil.ts

     javascript.lang.security.audit.detect-non-literal-fs-filename.detect-non-literal-fs-filename

        A variable is present in the filename argument of fs calls, this might allow an attacker to

        access anything on your system.

        Details: https://sg.run/8RNQ

  

         49┆ const fileData = fs.readFileSync(fixesPath + '/' + val).toString()

          ⋮┆----------------------------------------

        104┆ const fileData = fs.readFileSync(fixesPath + '/' + file).toString()

  
  

  server.ts

     ajinabraham.njsscan.eval_yaml_deserialize.yaml_deserialize

        User controlled data in 'yaml.load()' function can result in Remote Code Injection.

        Details: https://sg.run/Do0v

  

         43┆ const swaggerDocument = yaml.load(fs.readFileSync('./swagger.yml', 'utf8'))

          ⋮┆----------------------------------------

     ajinabraham.njsscan.good_helmet_checks.helmet_header_feature_policy

        Feature-Policy header is present. More information: https://helmetjs.github.io/docs/feature-

        policy/

        Details: https://sg.run/rdQP

  

        166┆ app.use(featurePolicy({

        167┆   features: {

        168┆     payment: ["'self'"]

        169┆   }

        170┆ }))

          ⋮┆----------------------------------------

     ajinabraham.njsscan.good_helmet_checks.helmet_header_frame_guard

        X-Frame-Options header is present. More information:

        https://helmetjs.github.io/docs/frameguard/

        Details: https://sg.run/b7YP

  

        163┆ app.use(helmet.frameguard())

          ⋮┆----------------------------------------

     ajinabraham.njsscan.good_helmet_checks.helmet_header_nosniff

        Content-Type-Options header is present. More information:

        https://helmetjs.github.io/docs/dont-sniff-mimetype/

        Details: https://sg.run/OPp7

  

        162┆ app.use(helmet.noSniff())

          ⋮┆----------------------------------------

     ajinabraham.njsscan.good_helmet_checks.helmet_header_x_powered_by

        Default X-Powered-By is removed or modified. More information:

        https://helmetjs.github.io/docs/hide-powered-by/

        Details: https://sg.run/kX31

  

        165┆ app.disable('x-powered-by')

          ⋮┆----------------------------------------

     ajinabraham.njsscan.good_ratelimiting.rate_limit_control

        This application has API rate limiting controls.

        Details: https://sg.run/dKon

  

         41┆ const RateLimit = require('express-rate-limit')

          ⋮┆----------------------------------------

     ajinabraham.njsscan.header_cors_star.generic_cors

        Access-Control-Allow-Origin response header is set to "*". This will disable CORS Same

        Origin Policy restrictions.

        Details: https://sg.run/Q5Xd

  

        158┆ app.options('*', cors())

          ⋮┆----------------------------------------

     javascript.lang.security.audit.code-string-concat.code-string-concat

        User controlled data in eval() or similar functions may result in Code Injection

        Details: https://sg.run/96Yk

  

        189┆ 'Preferred-Languages': [...new Set(locales.map((locale: { key: string }) => locale.key.substr(0, 2)))].join(', '),

  
  

  views/promotionVideo.pug

     javascript.express.security.audit.xss.pug.explicit-unescape.template-explicit-unescape

        Detected an explicit unescape in a Pug template, using either '!=' or '!{...}'. If external

        data can reach these locations, your application is exposed to a cross-site scripting (XSS)

        vulnerability. If you must do this, ensure no external data can reach this location.

        Details: https://sg.run/3xbe

  

         79┆ if (splitted.length != 2) {
````