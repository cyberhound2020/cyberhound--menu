
jogando = True
while jogando:
    #Você pode criar uma função que dê print o menu e retorne a dificuldade ou sair
    print("Dificuldades:")
    print("1 - Fácil")
    print("2 - Médio")
    print("3 - Difícil")
    print("\n4 - Sair")
    dificuldade = input("Digite a dificuldade desejada ou saia(Ex.: 1 OU `facil`): ")
    while dificuldade != '1' and dificuldade != '2' and dificuldade != '3' and dificuldade.lower() != 'facil' and dificuldade.lower() != 'medio' and dificuldade.lower() != 'dificil' and dificuldade != '4' and dificuldade.lower() != 'sair':
        dificuldade = input("\nEscolha Inválida!\nDigite a dificuldade desejada (Ex.: 1 OU `facil`): ")
    if dificuldade == '4' or dificuldade.lower() == 'sair':
        terminar = True
        jogando = False
    else:
        apresentaJogo()
    # enquanto não terminar
    while (not terminar):
       # processa jogada do jogador
       processaLanceJogador()
       # verifica Fechamento
       fechou = verificaFechamento()
       # atualiza sinalizador de encerramento do jogo
       terminar = (jogada == 9) or fechou == True
       # se for para terminar:
       if terminar:
          # exibe tabuleiro
          exibeTabuleiro()
          # termina o jogo
          break
      # processa jogada do computador
      if dificuldade == '1' or dificuldade.lower() == 'facil':
          processaLanceComputador(1) #OU processaLanceFacilComputador()
      elif dificuldade == '2' or dificuldade.lower() == 'medio':
          processaLanceComputador(2) #OU processaLanceMedioComputador()
      elif dificuldade == '3' or dificuldade.lower() == 'dificil':
          processaLanceComputador(3) #OU processaLanceDificilComputador()
      # verifica Fechamento
      fechou = verificaFechamento()
      # atualiza sinalizador de encerramento do jogo
      terminar = (jogada == 9) or fechou == True
      # exibe tabuleiro
      exibeTabuleiro()

      # em caso de fechamento, verifica vencedor e emite mensagem correspondente:
      if fechou:
      # se o vencedor for o jogador:
         if jogada in [1, 3, 5, 7, 9]:
             # emite mensagem de congratulação:
             print('Parabéns, você venceu!')
         # se o vencedor for o computador:
         else:
             # emite mensagem de zoação:
             print('Você é um pato!')
             # se a partida não fechou, emite mensagem de empate
      else:
         print('Deu velha !')
