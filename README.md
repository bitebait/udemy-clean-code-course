# 📚🐍 Meu repositório de estudos - Python Clean Coding

Repositório para praticar todo conteúdo absorvido durante o curso ["Python Clean Coding"](https://www.udemy.com/course/python-clean-coding) na plataforma Udemy.

<br>

*..algumas anotações sobre meu aprendizado durante o curso...*

* * *

## 📖 Acrônimos Importantes

- **DRY** - Don't Repeat Yourself.
- **KISS** - Keep It Simple Stupid.
- **YAGNI** - You Aren't Going to Need It.
- **SOC** -  Separation of Concerns.
- **NIH** - Not Invented Here.

* * *

## ✍️ Refatoração

### - O que é? 🤔

A refatoração tem como objetivo melhorar a estrutura (fundação) de um código sem alterar seu comportamento. Ao refatorar temos como objetivo limpar o código, tornando mais fácil de compreender, fazendo com que seja mais barato e rápido manter e consequentemente diminuindo problemas causados por bugs.

### - Por que? 🤔

Refatorar ajuda no amadurecimento do código, melhorando continuamente o design do software. Ajuda encontrar bugs, mantém o código limpo e consequentemente melhora o entendimento daquilo que foi escrito.

### - Algumas situações onde pode haver refatoração...
- Renomear arquivos.
- Renomear classes e métodos de classes.
- Renomear funções, rotinas e variáveis.
- Alterar assinaturas de métodos.
- Atualizar contratos entre métodos e classes.
- Mover a logica para cima na cadeia de herança.

* * *

## 🤯️ Comentários no código 

###  ✔️ Prós

- Melhor esclarecimento de código .
- Explica o **porquê** .
- Explica **como** .
- Planejamento, revisão e inclusão de recursos .
- Debbugging.

### ❌ Contras

- Os comentários apodrecem com o tempo. (seu comentário pode não refletir o momento atual do código).
- Adiciona sobrecarga (isso pode ser mitigado). 
- Adiciona ruído (apenas quando apodrecem).

** *Exemplos retirados do curso ["Python Clean Coding - Udemy"](https://www.udemy.com/course/python-clean-coding)*
#### Comentários inúteis:

```python
"""
Get Active Users
"""
def get_active_users(users):
	return [user for user in users if user.active]
```

#### Sem "porquê":

```python
"""
This code needs refactoring
"""
items = ('Python', 'PHP', 'JavaScript')

for x in items:
	do_something(x)
```

#### Rude:

```python
"""
This code is bad and you should feel bad
"""
class Order:
	username = ''
	last_logged_in = None
	total = 0
	items = []
	
	def __init__(self, username, last_logged_in, total, items):
		self.username = username
		self.last_logged_in = last_logged_in
		self.total = total
		self.items = items
```

#### Desatualizado / Contexto Errado:

```python
"""
PF: 25/05/2014
Loop over the pets and update the portfolio
"""
items = ('Python', 'PHP', 'JavaScript')

for x in items:
	portfolio_update()
	resume_update()
	
	# ...
	# Wait, what's `x` for again?
	do_something(x)
```

* * *

## 🚦  TDD - Test-driven development (benefício a longo prazo)


### - O que é? 🤔

Basicamente se baseia em pequenos ciclos de desenvolvimento, onde para cada nova funcionalidade desenvolvida escreve-se primeiros os testes antes mesmo de qualquer código. O teste inicial irá falhar(Red), então escrevemos um código que fará o teste passar(Green). Após o teste passar, é feita a refatoração(Refactor), onde as boas práticas serão aplicadas garantindo um código limpo, coeso e com baixo acoplamento. 


### - Por que? 🤔

Utilizar TDD duranto o desenvolvimento do seu projeto pode ter muitos benefícios como: 

- Feedback instantâneo sobre funcionalidades.
- Código mais limpo.
- Mais confiança durante a refatoração do código.
- Mais confiança durante a correção de bugs.
- Maior produtividade, já que gastará menos tempo caçando bugs e com depuradores.
- Ajuda a documentar aquilo que está sendo feito, melhorando o entendimento do propósito do código.


### ✔️ Boas Práticas

- Escreva testes claros e confiáveis, livres de bugs e que acompanhem o desenvolvimento do projeto. Lembre-se, nós passamos mais tempo lendo códigos que escrevendo.
- Mantenha os testes simples (Baby Steps).
- Escreva nomes descritivos para os testes, que descrevam de maneira simples e clara aquilo que esta sendo testado.
- Você deve ter uma meta de 100% de cobertura de código em funções com lógica real, evitando testar simples getters/setters.
- Execute seus testes com frequência para garantir que você nao tenha testes que falham intermitentemente.
- Evite dependências entre os testes. Executa-los de forma aleatória garantirá que seus testes não possuem dependências.

* * *

## ✒️  Nomeando...

** *Exemplos retirados do curso ["Python Clean Coding - Udemy"](https://www.udemy.com/course/python-clean-coding)*

### - Váriaveis

* * *

####  ❌ Exemplo ruim

```python
n = "William"
```

#### ✔️ Bom exemplo
```python
first_name = "William"
```

### - Nomeie suas váriaveis de maneira clara

* * *

####  ❌ Exemplo ruim - Oq significa o parâmetro 'u'?

```python
get_page(u)
```

#### ✔️ Bom exemplo
```python
URL = 'https://github.com'
get_page(URL)
```

### - Seja consistente

* * *

####  ❌ Exemplo ruim
```python
get_prod()
get_p_stock()
get_record_product()
```

#### ✔️ Bom exemplo
```python
get_product()
get_product_stock()
get_product_record()
```

### - Nome de funções
Os nomes das funções devem dizer o que estão fazendo com precisão e devem indicar o que é devolvido.

* * *

####  ❌ Exemplo ruim
```python
class Validation:
	
	def handle(self, val, max):
		if val < max:
			return False
		
validator = Validation()
# Oq 'handle' faz?
validator.handle(5, 6)
```

#### ✔️ Bom exemplo
```python
class Validation:
	
	def is_valid(self, val, max):
		if val < max:
			return False
		
validator = Validation()
validator.is_valid(5, 6)
```


