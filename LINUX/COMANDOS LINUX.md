# Comandos Básicos do Linux (Meu uso)

## Comandos Teclado

1. Comando para acender led do teclado que acende pela tecla **Scroll Lock**
    ```
    xset led named "Scroll Lock"
    ```



## Comandos para uso de HDs e SSDs

1. Comando utilizado para habilitar *Discos* que estão como **NTFS**
    ```
    sudo ntfsfix SEU_DISCO
    ```
    Substituir SEU_DISCO pelo caminho do seu disco. Exemplo: **/dev/sda2**  . Esse comando deve habilitar o disco para criação de pastas e manipulação de arquivos.


## Comandos para trabalhar com arquivos ZIP, RAR

### Arquivos RAR
1. Comando para instalar o descompactador de arquivos RAR
   ```
   sudo apt-get install unrar
   ```

2. Comando para verificar a integridade dos arquivos RAR e verificar os arquivos sem precisar extrair.
   ```
   unrar t arquivo.rar
   ```
   Substitua o nome **arquivo.rar** para verificar a integridade dos arquivos dentro do RAR.

3. Comando para extrair arquivos RAR sem senha
   ```
   unrar x arquivo.rar
   ```
   Substitua o **arquivo.rar** pelo nome do seu arquivo. Você deve estar dentro da pasta onde esta o arquivo que vai ser descompactado ou passe o caminho completo do arquivo.

4. Comando utilizado para descompactar arquivos RAR com senha
    ```
    unrar x -pSuaSenha arquivo.rar
    ```
    nesse comando se houver senha você deve substituir o **SuaSenha** com a senha correta do arquivo e também substituir o **ARQUIVO.RAR** pelo nome do seu arquivo que vai ser descompactado. Para descompactar você deve estar no mesmo diretorio do arquivo/pasta ou passe o caminho completo do arquivo.

5. Comando para compactar arquivos com senha
   ```
   zip -r -e -P minha_senha pasta_zipada.zip minha_pasta
   ``` 
   substituir **minha_senha** pela senha que deseja usar no arquivo ZIP, **pasta_zipada.zip** pelo nome que vai ter a pasta gerada e o nome da pasta que vai ser zipada **minha_pasta**.