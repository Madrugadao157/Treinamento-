# *Código do Jogo (em Python)*

```
import random

# Variáveis iniciais
jogador_vida = 100
jogador_fome = 50
jogador_sede = 50
jogador_dinheiro = 100
jogador_local = "Praia"
jogador_inventario = []

# Função para iniciar o jogo
def iniciar_jogo():
 global jogador_local
 print("Bem-vindo à Aventura na Ilha Misteriosa!")
 print("Você está na praia. O que fazer?")
 jogar()

# Função para jogar
def jogar():
 global jogador_vida
 global jogador_fome
 global jogador_sede
 global jogador_dinheiro
 global jogador_local
 global jogador_inventario
 
 print("\nLocal:", jogador_local)
 print("Vida:", jogador_vida)
 print("Fome:", jogador_fome)
 print("Sede:", jogador_sede)
 print("Dinheiro:", jogador_dinheiro)
 print("Inventário:", jogador_inventario)
 
 escolha = input("\nEscolha (1) Explorar, (2) Descansar, (3) Mover-se, (4) Comprar, (5) Inventário: ")
 
 # Praia
 if jogador_local == "Praia":
 if escolha == "1":
 print("Encontrou um mapa!")
 jogador_inventario.append("Mapa")
 jogador_local = "Floresta"
 elif escolha == "2":
 print("Descansou. Vida +10")
 jogador_vida += 10
 jogador_fome -= 10
 jogador_sede -= 10
 elif escolha == "3":
 print("Mover-se para onde? (1) Floresta, (2) Caverna")
 mover = input()
 if mover == "1":
 jogador_local = "Floresta"
 elif mover == "2":
 jogador_local = "Caverna"
 elif escolha == "4":
 print("Comprar o que? (1) Água, (2) Comida")
 comprar = input()
 if comprar == "1":
 jogador_dinheiro -= 20
 jogador_sede += 20
 elif comprar == "2":
 jogador_dinheiro -= 30
 jogador_fome += 30
 
 # Floresta
 elif jogador_local == "Floresta":
 if escolha == "1":
 print("Encontrou uma chave!")
 jogador_inventario.append("Chave")
 jogador_local = "Caverna"
 elif escolha == "2":
 print("Descansou. Vida +10")
 jogador_vida += 10
 jogador_fome -= 10
 jogador_sede -= 10
 
 # Caverna
 elif jogador_local == "Caverna":
 if escolha == "1":
 print("Encontrou o tesouro!")
 print("Você ganhou!")
 elif escolha == "2":
 print("Descansou. Vida +10")
 jogador_vida += 10
 jogador_fome -= 10
 jogador_sede -= 10
 
 # Condições de derrota
 if jogador_vida <= 0:
 print("Game Over! Você morreu.")
 elif jogador_fome <= 0:
 print("Game Over! Você morreu de fome.")
 elif jogador_sede <= 0:
 print("Game Over! Você morreu de sede.")
 else:
 jogar()

# Iniciar o jogo
iniciar_jogo()
```
