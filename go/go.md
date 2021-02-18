**Variáveis:**

* :=    - utilizado para criar novas variáveis, dentro de code blocks
* =     - para atribuir valores e variáveis já existentes
* var   - utilizado para criar novas variáveis, não precisa estar dentro de code blocks

*Exemplos:*

```
package main

import (
    "fmt"
)

var y = 10;
var z int = 12;

func main() {
    x := 10;
    x = 20;
    fmt.Println(x, y, z)
}
```

Não da pra fazer atribuição de valor em variáveis declaradas com var fora de scopo, ex:

```
package main

import (
    "fmt"
)

var y = 10;
y = 20; //error

func main() {
    fmt.Println(y)
}
```

**Tipos:**

* Tipos em GO são estáticos, ou seja, declarou uma variável de um tipo, não tem como reatribuir ela a outro tipo

Tipos de dados primitivos básicos:

* int
* string
* bool

Tipos de dados compostos:

* slice
* array
* struct
* map

**Retorno de função:**

```
package main

import (
    "fmt"
)

func main() {
    y := 10
    result, error := fmt.Println(y)
    fmt.Println(result, error);
}
```

Se não quiser pegar algum valor do retorno da função usa o "_":

```
package main

import (
    "fmt"
)

func main() {
    y := 10
    _, error := fmt.Println(y)
    fmt.Println(error);
}
```

nil == null //true

string interpretadas = "oi \n tudo bom?\t simm"

string raw = `"oi \n tudo bom?\t simm"`

**Criando seu próprio tipo no go:**

```
package main

import (
    "fmt"
)

type hotdog int
var b hotdog

func main() {
    fmt.Printf("%T", b) // main.hotdog
}
```

