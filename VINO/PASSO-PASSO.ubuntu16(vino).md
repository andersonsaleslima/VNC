Vino-Server 
==================================================================================

1- Ao logar com o usu�rio n�o root execute:

	vino-preferences


2- Preencha os campos solicitados com as informa��es abaixo:

	> Compartilhamento
		- Permitir que outros usu�rios vejam sua ar�a de trabalha: true
		- Permitir que outros usu�rios controlem sua �rea de trablaho: true
	> Seguran�a
		- Voc� deve confirmar cada acesso � esta m�quina: false
		- Exigir que o usu�rio digite esta senha: ******
		- Automaticamente configurar roteador UPnP para abrir e encaminhar portas: false
	> Mostrar �cone da �rea de notifica��es: Nunca

<span style="display:block;text-align:center">![vino-preferences](img/1.vino-preferences.png)</span>

3- Criar script "vino.sh" para habilitar Vino-Server.

		#!/bin/bash

		exec > vino.log

		export DISPLAY=:0
		gsettings set org.gnome.Vino enabled true
		gsettings set org.gnome.Vino require-password false
		/usr/lib/vino/vino-server &

4- Atribuir permis�o de execu��o ao script

	chmod +x vino.sh

5- Colocar script na inicializa��o do usu�rio

	echo "./vino.sh" >> /home/user/.profile 

		
