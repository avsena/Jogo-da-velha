Program Pzim ;
uses
crt;
procedure velhinha;
begin
end;
procedure quiz1;
var

resposta:array[1..5] of string;
pontu:integer;
score:integer;



begin
score := 0;
clrscr;

writeln ('            VOCÊ ENTENDE DE LOGICA DE PROGRAMAÇÃO?            ');

writeln ('  PERGUNTA 1: Oque é um vetor                ') ;
begin
read (    resposta[1]);
	 if (   resposta[1] = 'teste') then
	 begin
	 score:= score + 1;
	writeln ('       VOCE ACERTOU MEN, BOA!       ');
	end
	else
	
	writeln ('ERROU PARCA');
	
	writeln  ('   >>>>> Próxima Pergunta ( Digite uma tecla para próxima pergunta)         ');
	readkey;
	 
clrscr;
writeln ('PERGUNTA 2:  Oque é um procedimento        ');
read (   resposta[2]);
  if (    resposta[2] = 'teste 2') then
  begin
  score := score + 1;
 writeln ('VOCE ACERTOU BRO!');
  end
  else 
 
 writeln ('ERROU KK');
 writeln ('            >>>>> Próxima Pergunta ( Digite uma tecla para próxima pergunta)    ');
 readkey; 
  
  
clrscr;  

writeln ('PERGUNTA 3: Oque é uma função         ');
read(    resposta[3]) ;
   if (resposta[3] = 'teste 3') then
	 begin 
	 score := score + 1;
	 writeln ('MAIS UMA REPOSTA CERTA! NICE!');
	 end
	 else
	 writeln ('ERROU');
	 writeln ('          >>>>> Próxima Pergunta ( Digite uma tecla para próxima pergunta)    ');
	 readkey;
	 
	 
	 writeln ('        OK   SEU RESULTADO FINAL EM PONTOS FOI',score); 
	 
	   
		
	
				end;
		
end;

procedure quiz2;
 
begin
clrscr;
writeln ('          QUIZ LÓGICA                   ');
end;



procedure jogodavelha;
var
resp:integer;
campo:array[1..3,1..3] of string;
vez,jogada,numero_jogadas:integer;
cont:integer;
cont_jogador:integer;
jogada_ok:boolean;
jogador:array [1..2] of string;
vencedor:integer;
simbolo:string;
l,c:integer;
begin
  for l:= 1 to 3 do
  begin
    for c:= 1 to 3 do
    begin
      campo[l,c] := ' ';
    end;
  end;
  
  begin
    for cont_jogador:= 1 to 2 do
    begin
      gotoxy (35,3);
      writeln ('JOGADORES');
      gotoxy (25,5);
      write ('Digite o nome do JOGADOR ',cont_jogador,': ');
      read(jogador[cont_jogador]);
      clrscr;
    end;
    
    
    
    
    
    
    //Exibe instruções
    gotoxy(35,3);
    writeln('INSTRUÇÕES');
    gotoxy (15,5);
    writeln ('O Jogador 1 começa, digite o numero de 1 a 9 usando');
    gotoxy (15,6);
    writeln ('o teclado numerico correspondente as ''casas'', quem');
    gotoxy (15,7);
    writeln ('completar uma linha vertical horizontal ou diagonal');
    gotoxy (15,9);
    writeln ('PRESSIONE QUALQUER TECLA PARA COMEÇAR...');
    readkey;
    clrscr; // Limpa a tela
    
    numero_jogadas:= 0;
    simbolo:= 'X';
    cont_jogador:=1;
    vencedor:= 0;
    
    
     while (vencedor=0) do
     begin
    //Desenha o jogo da velha
      
      
      writeln;
      gotoxy(30,5);
      writeln('  ', campo[1, 1], ' | ', campo[1, 2], ' | ', campo[1, 3]);
      gotoxy(30,6);
      writeln(' -----------');
      gotoxy(30,7);
      writeln('  ', campo[2, 1], ' | ', campo[2, 2], ' | ', campo[2, 3]);
      gotoxy(30,8);
      writeln(' -----------');
      gotoxy(30,9);
      writeln('  ', campo[3, 1], ' | ', campo[3, 2], ' | ', campo[3, 3]);
      writeln;
      gotoxy(15,2);
      writeln ('Jogador 1 ',jogador[1],'= X');
      gotoxy(45,2);
      writeln ('Jogador 2 ',jogador[2],'= O');
      gotoxy (25,12);
      
       repeat
      write ('VEZ DO JOGADOR ',cont_jogador,': ');
      read(jogada);
      clrscr;
      case (jogada) of
        1:
        begin
          if (campo[3,1] = ' ') then
          begin
            campo[3,1]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        2:
        begin
          if (campo[3,2] = ' ') then
          begin
            campo[3,2]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        3:
        begin
          if (campo[3,3] = ' ') then
          begin
            campo[3,3]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        4:
        begin
          if (campo[2,1] = ' ') then
          begin
            campo[2,1]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        5:
        begin
          if (campo[2,2] = ' ') then
          begin
            campo[2,2]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        6:
        begin
          if (campo[2,3] = ' ') then
          begin
            campo[2,3]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        7:
        begin
          if (campo[1,1] = ' ') then
          begin
            campo[1,1]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        
        8:
        begin
          if (campo[1,2] = ' ') then
          begin
            campo[1,2]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;
        end;
        9:
        begin
          if (campo[1,3] = ' ') then
          begin
            campo[1,3]:=simbolo;
            jogada_ok:=true;
          end
          else
          jogada_ok:=false;

        end;
        
      end;//Termina case
        
        
      until (jogada_ok = true);//fim repeat
        
        numero_jogadas := numero_jogadas + 1;
        
        //Verifica se há algum jogador
        if (campo[1, 1] = campo[1, 2]) and (campo[1, 2] = campo[1, 3]) and (campo[1, 3] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[2, 1] = campo[2, 2]) and (campo[2, 2] = campo[2, 3]) and (campo[2, 3] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[3, 1] = campo[3, 2]) and (campo[3, 2] = campo[3, 3]) and (campo[3, 3] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[1, 1] = campo[2, 1]) and (campo[2, 1] = campo[3, 1]) and (campo[3, 1] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[1, 2] = campo[2, 2]) and (campo[2, 2] = campo[3, 2]) and (campo[3, 2] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[1, 3] = campo[2, 3]) and (campo[2, 3] = campo[3, 3]) and (campo[3, 3] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[1, 1] = campo[2, 2]) and (campo[2, 2] = campo[3, 3]) and (campo[3, 3] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (campo[1, 3] = campo[2, 2]) and (campo[2, 2] = campo[3, 1]) and (campo[3, 1] <> ' ') then
        begin
          vencedor := cont_jogador;
        end
        else if (numero_jogadas = 9) then
        begin
          vencedor := 3;
        end;
        if (cont_jogador = 2) then
      begin
         cont_jogador := 1;
         simbolo:= 'X';
      end
      else
      begin
         cont_jogador := 2;
         simbolo:= 'O';
      end;
      
      
      
   
        
      end;//FIM WHILE
      
       clrscr; // Limpa a tela
  writeln;
  writeln('  ', campo[1, 1], ' | ', campo[1, 2], ' | ', campo[1, 3]);
  writeln(' -----------');
  writeln('  ', campo[2, 1], ' | ', campo[2, 2], ' | ', campo[2, 3]);
  writeln(' -----------');
  writeln('  ', campo[3, 1], ' | ', campo[3, 2], ' | ', campo[3, 3]);
  writeln;
     
  if (vencedor = 1) then
  begin
    write('            Parabens :',jogador[1],'!Voce ganhou                ');
    write ('      >>>>>>>>> O JOGO NÃO ACABOU! <<<<<<<<                     ');
    writeln ('             (Pressione uma tecla)                            '); 
    readkey;
    quiz1;
    
 
    
  end
  else if(vencedor = 2) then
  begin
    write(' Parabens :', jogador[2],'!Voce ganhou!');
    write ('      >>>>>>>>> O JOGO NÃO ACABOU! <<<<<<<<             ');
    writeln ('             (Pressione uma tecla)                    '); 
    readkey;
    
         quiz2;
  
  
 
  
  end
  else
  begin
    write(' Ops... Deu velha...');
  end;
  
								 
        
    end;//FIM DO PROCEDIMENTO
    end;
    
    //PROCEDIMENTO MENU
    procedure menu();
    var
    resp:integer;
    begin
      gotoxy(19,3);
      writeln('     __                 ____ _   __    ____');
      gotoxy(19,4);
      writeln(' __ / /__  ___ ____  __/ / /| | / /__ / / /  ___ _');
      gotoxy(19,5);
      writeln('/ // / _ \/ _ `/ _ \/_  . __/ |/ / -_) / _ \/ _ `/');
      gotoxy(19,6);
      writeln('\___/\___/\_, /\___/_    __/|___/\__/_/_//_/\_,_/');
      gotoxy(19,7);
      writeln('         /___/      /_/_/                        ');
      
      gotoxy(23,9);
      writeln('***************************************');
      gotoxy(23,10);
      writeln('*            1-Iniciar Jogo           *');
      gotoxy(23,11);
      writeln('*            2-Desenvolvedores        *');
      gotoxy(23,12);
      writeln('***************************************');
      gotoxy(25,13);
      write('Escolha uma opção: ');
      readln(resp);
      clrscr;
      if (resp = 1) then
      jogodavelha;
    end;
    
      
    
    
    
    
    //PROGRAMA PRINCIPAL
    
    Begin
      menu();
End.
