# CHECKUSER PARA O APP CONECTA4G!




```
apt install wget -y; bash <(wget -qO- raw.githubusercontent.com/Cyber-ssh/cyber4g/main/instcheck.sh)
```
elif [[ "$resposta" = '3' ]]; then
		clear
		if ps x | grep -w WebSocket | grep -v grep 1>/dev/null 2>/dev/null; then
		figlet 'SSH-PLUS' | lolcat
		echo -e "\E[41;1;37m       🚀   WEBSOCKET SECURITY   🚀           \E[0m"
				echo ""
				fun_wsswsocksoff() { 
					pkill WebSocket
					for pidproxy in $(screen -ls | grep ".ws" | awk {'print $1'}); do
						screen -r -S "$WebSocket" -X quit
					done
					[[ $(grep -wc "WebSocket" /etc/autostart) != '0' ]] && {
						sed -i '/WebSocket/d' /etc/autostart
					}
					sleep 1
					screen -wipe >/dev/null
				}
				echo -e "\033[1;32mDESATIVANDO O WEBSOCKET SECURITY\033[1;33m"
				echo ""
				fun_bar 'fun_wsswsocksoff'
				echo ""
				echo -e "\033[1;32mWEBSOCKET SECURITY DESATIVADO COM SUCESSO!\033[1;33m"
				
				fun_socks
			else
			figlet 'SSH-PLUS' | lolcat
		echo -e "\E[44;1;37m       🚀   WEBSOCKET SECURITY   🚀           \E[0m"
				echo ""
				rm -rf /etc/mamalista
				read -p "$(echo -e "★ \033[1;32mQUAL PORTA ULTILIZAR? \033[1;37m")" -e -i 80 cuzin
				echo "$cuzin" > /etc/mamalista
				echo ""
				read -p "$(echo -e "★ \033[1;32mQUAL MENSAGEM PARA STATUS? \033[1;37m")" -e -i WebSecurity cuzin2
				rm -rf /etc/mamalista2
				echo "$cuzin2" > /etc/mamalista2
				[[ -z "cuzin" ]] && {
					echo ""
					echo -e "\033[1;31mPorta invalida!"
					
				fun_socks
				}
				verif_ptrs $porta
				fun_iniwssocks() {
					sleep 1
					screen -dmS novoWS /etc/SSHPlus/WebSocket -proxy_port 0.0.0.0:$(cat /etc/mamalista)
					[[ $(grep -wc "WebSocket" /etc/autostart) = '0' ]] && {
						echo -e "screen -dmS novoWS /etc/SSHPlus/WebSocket -proxy_port 0.0.0.0:$(cat /etc/mamalista)
					} || {
						sed -i '/WebSocket/d' /etc/autostart
						echo -e "screen -dmS novoWS /etc/SSHPlus/WebSocket -proxy_port 0.0.0.0:$(cat /etc/mamalista)
					}
				}
				echo ""
				echo -e "\033[1;32mINICIANDO O WEBSOCKET SECURITY\033[1;33m"
				echo ""
				fun_bar 'fun_iniwssocks'
				echo ""
				echo -e "\033[1;32WEBSOCKET SECURITY ATIVADO COM SUCESSO\033[1;33m"
				
				fun_socks
			fi