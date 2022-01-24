# ShellScript

Esse Script é voltado para consumir a API do zabbix e criar grupos de hosts.

Preencha as Variaveis:

Preencha com Usuário do Zabbix:
ZABBIX_USER=""

 Preencha com a senha do Zabbix:
ZABBIX_PASS=""

 Mude "ip" para o ip do zabbix-web:
ZABBIX_API="http://ip/api_jsonrpc.php" 

Na opção "name", observamos que está setado com "$1", que signifca ser o primeiro parametro, sendo assim para criar um grupo o comando seria:

./api.sh teste 

O $1 foi definido como teste na linha de comando. 

Para criar diversos grupos de hosts através de uma lista, utilize "For".

for i in $(cat lista.txt) ; do  HOSTNAME_LISTA=$(echo $i| cut -d\; -f1) ; ./group.sh ${HOSTNAME_LISTA}"  ; done

Substituia "lista.txt" por sua lista com os nomes dos hosts.
