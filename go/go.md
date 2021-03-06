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

**Conversão de tipos:**

*o tipo hotdog é gerado a partir do tipo int, mas quando atribuimos uma variavel do tipo hotdog em uma variavel do tipo int isso não funciona,
porrque os tipos são diferentes. Segue exemplo do erro abaixo:*

```
package main

import (
	"fmt"
)

type hotdog int

var b hotdog = 10

func main() {
	a := 10
	a = b // cannot use b (type hotdog) as type int in assignment
	fmt.Printf("%v\n", a)
}
```

*Para resolver isso iremos usar conversão de tipo:*

```
package main

import (
	"fmt"
)

type hotdog int

var b hotdog = 10

func main() {
	a := 10
	a = int(b)
	fmt.Printf("%v\n", a)
}
```

*for*

```
package main

import (
	"fmt"
)

func main() {
	for x := 0; x < 10; x++ {
		fmt.Println(x)
	}
}
```

```
package main

import (
	"fmt"
)

func main() {

    x := 0

	for x < 10 {
		fmt.Println(x)
        x++
	}
}
```

*array*

```
package main

import (
	"fmt"
)

var x [5]int

func main() {
	x[0] = 1
	x[1] = 2
    array := [5]int{1, 2, 3, 4, 5}
	fmt.Println(x[0], x[1])
	fmt.Println(x)
    fmt.Println(len(x))
}
```

*slice*

```
package main

import (
	"fmt"
)

var x [5]int

func main() {
	x := []int{1, 2, 3, 4, 5}
    fmt.Println(x)

    y := append(x, 6)
    fmt.Println(y)
}
```

