- Gerando hash md5 nativamente

```
const crypto = require('crypto')

let hash = crypto.createHash('md5').update('some_string').digest("hex")
```