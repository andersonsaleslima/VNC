Vino-Server 
==================================================================================

1- Criar script para habilitar Vino-Server

	nano vino.sh

		#!/bin/bash

		exec > vino.log

		export DISPLAY=:0
		gsettings set org.gnome.Vino enabled true
		gsettings set org.gnome.Vino require-password false
		/usr/lib/vino/vino-server &

![vino-preferences](img/vino-preferences.png)


2- Atribuir permisão de execução ao script

	chmod +x vino.sh

3- Colocar script na inicialização do usuário

	echo "./vino.sh" >> /home/user/.profile

		
