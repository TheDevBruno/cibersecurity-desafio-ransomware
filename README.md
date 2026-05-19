
Com base nos arquivos presentes no repositório do desafio (`encrypter.py` e `decrypter.py`), o projeto demonstra de forma conceitual o funcionamento de processos de criptografia e descriptografia simétrica utilizando a biblioteca `pyaes`.

Abaixo está a descrição técnica do fluxo de funcionamento de cada arquivo para auxiliar na documentação e elaboração do seu `README.md`:

---

### 1. `encrypter.py` (Processo de Criptografia)
Este script simula a ação de encriptação em um arquivo de texto de demonstração (`teste.txt`):

1. **Leitura dos Dados:** O arquivo alvo (`teste.txt`) é aberto em modo de leitura binária (`"rb"`), e todo o seu conteúdo é carregado para a memória.
2. **Remoção do Arquivo Original:** Para simular a indisponibilidade do dado original, o arquivo em texto plano é excluído do sistema operacional usando `os.remove()`.
3. **Inicialização da Criptografia Simétrica:** Uma chave estática de 16 bytes (`b"testeransomwares"`) é definida. O algoritmo AES (Advanced Encryption Standard) é configurado no modo de operação CTR (Counter Mode) através da biblioteca `pyaes`.
4. **Geração do Arquivo Criptografado:** Os dados lidos são submetidos à função de encriptação (`aes.encrypt`). O resultado binário criptografado é então gravado em um novo arquivo com a extensão modificada (`teste.txt.ransomwaretroll`).

---

### 2. `decrypter.py` (Processo de Descriptografia)
Este script realiza o processo inverso, demonstrando a recuperação dos dados mediante a posse da chave criptográfica correta:

1. **Leitura do Arquivo Criptografado:** O script abre o arquivo gerado na etapa anterior (`teste.txt.ransomwaretroll`) em modo binário e lê seu conteúdo encriptado.
2. **Descriptografia:** Utilizando a mesma chave estática de 16 bytes e o mesmo modo de operação (AES-CTR), a função `aes.decrypt` reverte os bytes encriptados para o formato original em texto plano.
3. **Limpeza do Arquivo Criptografado:** O arquivo com extensão `.ransomwaretroll` é excluído do disco.
4. **Restauração do Arquivo Original:** Um novo arquivo chamado `teste.txt` é recriado em modo de escrita binária (`"wb"`) e preenchido com os dados originais restaurados.

---

### Tópicos Recomendados para o seu `README.md`
Para construir um perfil de destaque na entrega do projeto, você pode estruturar seu README com os seguintes pontos:
* **Objetivo do Projeto:** Demonstrar de forma prática e didática o conceito de encriptação simétrica de ponta a ponta.
* **Tecnologias Utilizadas:** Python 3 e a biblioteca `pyaes`.
* **Conceitos de Segurança Abordados:** Criptografia simétrica (AES), gestão e importância das chaves criptográficas para a integridade e confidencialidade dos dados.
* **Instruções de Uso (Passo a Passo):** Explicar como rodar primeiro o `encrypter.py` para ver a transformação do arquivo e, em seguida, o `decrypter.py` para verificar a restauração.
