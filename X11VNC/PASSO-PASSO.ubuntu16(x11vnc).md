Ubunutu 16 - X11VNC
==================================================================================

1- Atualizar sistema e instalar x11vnc.

	apt-get install -y update 
	apt-get install -y x11vnc

2- Criar um diretório e um arquivo para armazenar a senha de acesso ao VNC.

	mkdir /root/.vnc 
	touch /root/.vnc/passwd

3- Criar senha de acesso ao VNC no arquivo criado.

	x11vnc -storepasswd <PASSWORD> /root/.vnc/passwd

4- Adicinioar "x11vnc" ao Systemd criando o arquivo "/lib/systemd/system/x11vnc.service" 
com o seguinte conteúdo.

		[Unit]
		Description=Start x11vnc at startup.
		After=multi-user.target

		[Service]
		Type=simple
		ExecStart=/usr/bin/x11vnc -auth guess -forever -loop -noxdamage -repeat -rfbauth /home/root/.vnc/passwd -rfbport 5900 -shared

		[Install]
		WantedBy=multi-user.target

5- Executar seguintes comandos para validar a inicialização do x11vnc junto ao sistema.

	systemctl daemon-reload
	systemctl enable x11vnc.service

6- Iniciar serviço "x11vnc" pelo "systemd" e verificar seu status.

	systemctl start x11vnc
	systemctl status x11vnc
