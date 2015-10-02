# Delphi_Remote_Access_PC
Remote access in Delphi 7 and Delphi XE5 (With sharer files, CHAT and Forms Inheritance)

Acesso Remoto em Delphi 7 e Delphi XE5 (Com Compartilhador de Arquivos, CHAT e Herança de Formulários) 



				Esta source foi criada por Maickonn Richard.
				Contato: senjaxus@gmail.com
				
				A distribuição desta source é gratuita!
				NÃO ME RESPONSABILIZO PELO MAU USO DESTA SOURCE.

------------------------------------------------------------------------------


Provavelmente quando você abrir o projeto, vai aparecer uma mensagem falando que falta componente.
O que você deve fazer é seguir os seguintes passos:


<strong>-> Delphi 7:</strong>
* Com o Delphi aberto, vá ao menu "Component"
* Em seguida clique em "Install Packages..."
* Clique no botão "Add"
* Vá no diretório onde o Delphi está instalado e entre na pasta "Bin". ( C:\Program Files (x86)\Borland\Delphi7\Bin )
* Selecione o arquivo "dclsockets70.bpl" e clique em Abrir.
* Feche o Delphi e abra o projeto novamente.

<strong>-> Delphi XE5:</strong>
* Com o Delphi aberto, vá ao menu "Component"
* Em seguida clique em "Install Packages..."
* Clique no botão "Add"
* Vá no diretório onde o Delphi está instalado e entre na pasta "Bin". ( C:\Program Files (x86)\Embarcadero\RAD Studio\12.0\bin )
* Selecione o arquivo "dclsockets190.bpl" e clique em Abrir.
* Feche o Delphi e abra o projeto novamente.


<strong>Na pasta Units, você encontrará:</strong>
* Unit zLibEx.pas com a pasta zLib - Usada para comprimir dados. (Você deve copiar a pasta zLib para dentro do Projeto).
* StreamManager.pas - Criada para capturar a tela, e fazer a comparação.
* SndKeys32.pas - Serve para simular tecla pressionada.




-----------------------------------------------------------------------------

<strong>Entendendo o funcionamento do Software.</strong>

* Cliente conecta com o servidor. Ao conectar o primeiro Socket ele irá conectar os outros,
que definem se vai ser para transferência de imagens, download e upload de arquivos ou de teclado remoto.
O primeiro Socket transfere mensagens, a posição, e o clique do mouse.

* Servidor pede a primeira imagem. Cliente irá capturar a tela (Captura é feita em Bitmap, 8bit para reduzir o tamanho)
então ele irá receber uma compressão zLib. Após a compressão irá enviar a primeira
imagem e logo após salvará a mesma na memória.
Quando o servidor receber a imagem ele irá requisitar outra, onde o cliente irá comparar com a antiga e enviar só
o que foi alterado. (Sempre comprimindo os dados).