
## Inicializando o Container 

<code>

    docker build -t crypto-etl:latest .
    docker compose up    

    # Novo console
    docker exec -it crypto-etl-01 bash
    docker exec -it crypto-etl-01 python ./src/main.py  
   

</code>


### Comandos de verificação

<code>
    docker inspect crypto-etl-01
    docker logs --tail 50 --follow crypto-etl-01
</code> 

Verificar se o Mount corresponde ao formato correto com o comando  `docker inspect crypto-etl-01`

<code>
    "Mounts": [
                {
                    "Type": "bind",
                    "Source": "D:\\Projetos\\Trade\\CryptoETL\\src",
                    "Destination": "/app/src",
                    "Mode": "rw",
                    "RW": true,
                    "Propagation": "rprivate"
                }
            ],
</code>

### Finalizando:
<code>
    docker stop crypto-etl-01   &&    docker rm crypto-etl-01
</code>