# Lojinha-do-Z-
#aprendendo a criar lojinhas simples em Python
Nome = ['Cenoura','Maça']
Preco = [4.89,8.34]
Estoque = [32,24]
Venda = [None,None]

menu = f"""
  {'-'*25}\n  Bem vindo a Lojinha do Zé\n  {'-'*25}
  \n  0 -- Fim\n  1 -- Adicionar Produtos\n  2 -- Vender Produtos\n  3 -- Listar Produtos
  Escolha: """

def Main():
  while True:
    E= int(input(menu))
    if E == 0:
      break
    elif E == 1:
      adiciona_prod()
    elif E == 2:
      vendendo()
    elif E == 3:
      listando_prod()

def adiciona_prod():
  print("Adicionando um Produto Novo!!")
  nome= input("Nome do Produto: ").title()
  if nome in Nome:
    print("Este Produto Já existe no Sistema.")
  else:
    preco = float(input("Preço do Produto: "))
    estoque = float(input("Quantidade do Produto: "))
    
    Nome.append(nome)
    Preco.append(preco)
    Estoque.append(estoque)
    Venda.append(None)
    print("\nProduto Adicionado com Sucesso!")

def vendendo():
  print("Vendendo Produto")
  nome_prod = input("Nome do produto: ").title()
  if nome_prod in Nome:
    i=Nome.index(nome_prod)
    print(f"\n Nome {Nome[i]}\n Preço {Preco[i]}\n Estoque {Estoque[i]}\n")
    qtd_vendida=int(input("Quantos foram vendidos"))
    if qtd_vendida < Estoque[i]:
      Venda[i] = qtd_vendida
      Estoque[i] = (Estoque[i] - qtd_vendida)
      print(f"\nFoi vendido {qtd_vendida} do Produto {Nome[i]}s, sobrou {Estoque[i]}{Nome[i]}s")
    else:
      print("NÃO HÁ ESTOQUE PARA ESSA VENDA!")
    
  else:
    print("Produto não encontrado")
def listando_prod():
  print("Listando Dados\nVocê deseja Listar todos os produtos aperte S\n Caso deseje apenas um produto aperte N")
  veri= input("").upper()
  if veri == 'S':
    print("TODOS PRODUTOS CADASTRADOS:\n")
    for i  in Nome:
      print(f"Nome    {Nome[Nome.index(i)]}\nPreço   {Preco[Nome.index(i)]}\nEstoque {Estoque[Nome.index(i)]}\nVendido {Venda[Nome.index(i)]}\n{'-'*15}")
    

if __name__ == '__main__':
  Main()

print(Nome,Estoque,Venda)
