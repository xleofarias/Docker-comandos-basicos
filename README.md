<h1>Docker-comandos-basicos</h1>

<h2>Guia de comandos básicos pra o Docker</h2>

1. Docker run - cria e executa um container de acordo com a imagem escolhida.
2. Docker run - Usando com a frag -v podemos criar um volume onde ficará os arquivos mesmo depois do container ter sido destruído. docker run -v /home/leo/volume-docker:/app -it ubuntu bash 
3. Docker pull - faz o download de uma imagem do DockerHub.
4. Docker ps - mostra os containers em exercução.
5. Docker ps -a - mostra os containers que estão ativos e não ativos.
6. Docker images - mostra as imagens que tem no host.
7. Docker exec - executa um comando para em um container.
8. Docker history - mostra todas as camadas da imagem.
9. Docker inspect - dar informações da imagem ou do container.
10. Docker build - Utilizamos para poder usar o arquivo Dockerfile e iniciar o container com todas as dependencias do arquivo. Parametros -t para dar nome a imagem.
11. Docker stop $(docker container ls -q)
12. Docker login -u - serve para logar na sua conta do DockerHub na sua maquina.
13. Docker push nome da imagem - É utilizado para enviar a imagem para o DockerHub.
14. Docker network ls - Para saber as redes ativas no host.

<h3>Guia para o Dockerfile</h3>

- FROM - É o nome e a versão da imagem. Exemplo: node:latest
- WORKDIR - É a pasta onde o container irá trabalhar, podemos criar ela dentro do arquivo por exemplo /app-node
- COPY - É onde iremos copiar o conteúdo do projeto e onde ele vai se usado, então sera na pasta atual "." e dentro da pasta /app-node que vai ficar também representado pelo ".".
- RUN - O nome do comando que iremos executar, exemplo npm install.
- ARG - Serve para colocar a variavel de ambiente, mas ela só serve no momento da criação do container, exemplo ARG PORT=6000
- ENV - Praticamente igual ao ARG mas ele serve para se usar dentro do container, exemplo ENV $PORT 
- ENTRYPOINT - O ponto de entrada do processo, aqui iremos iniciar o npm. usando o comando npm start. 
- EXPOSE - Serve para quem for usar o dockerfile e a aplicação for web saber em qual porta ela está exposta, exemplo 3000.
