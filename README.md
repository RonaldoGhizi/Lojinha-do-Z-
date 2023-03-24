# Lojinha-do-Z-
#aprendendo a criar lojinhas simples em Python 
nome = []
preco = []
estoque = []
venda = []


def menu():
  print("", "-" * 25, "\n Bem vindo a Lojinha do Zé\n", "-" * 25)
  print(" 0 -- Fim")
  print(" 1 -- Adicionar Produtos")
  print(" 2 -- Vender Produtos")
  print(" 3 -- Listar Produtos\n")


def rodando():
  res = 5
  try: 
    if type(res) == int:
      while res != 0:
        menu()
        res = int(input(" O Que Deseja? "))
        if res == 1:
          nome_ad = input(" Digite o Nome do Produto: ").title()
          preco_ad = float(input(" Digite o Preço do Produto: "))
          estoque_ad = float(input(" Quantidade de produtos em estoque: "))
          nome.append(nome_ad)
          preco.append(preco_ad)
          estoque.append(estoque_ad)
          venda.append(0)
          print(" {} Foi adicionado(a) á Lojinha!".format(nome_ad))
        elif res == 2:
          nomvenda = input(
            "Digite o Nome do produto que deseja vender: ").title()
          if nomvenda in nome:
            i = nome.index(nomvenda)
            print("\nO produto é {} o preço é {} tem no estoque {}\n".format(
              nome[i], preco[i], estoque[i]))
            vendido = (int(input("Quanto do {} foi vendido: ".format(nome[i]))))
            if vendido > estoque[i]:
              print("O produto possui apenas {} no estoque!".format(estoque[i]))
            elif vendido < estoque[i]:
              estoque[i] = estoque[i] - vendido
              venda.insert(i, vendido)
              print("Agora tem  {}  {}s no estoque\n".format(
                estoque[i],nome[i] ))
        elif res == 3:
          print("-"*25)
          print("Nome    :{}\nEstoque :{}\npreço   :{}\nVendido :{}".format(nome,estoque,preco,venda))
          print("-"*25)
          input("Enter Para continuar ")
  except:
    print("\nVoce Digitou algo de errado aperte enter para finalizar")
    
rodando()
