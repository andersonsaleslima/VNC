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

2- Atribuir permis�o de execu��o ao script

	chmod +x vino.sh

3- Colocar script na inicializa��o do usu�rio

	echo "./vino.sh" >> /home/user/.profile

		
