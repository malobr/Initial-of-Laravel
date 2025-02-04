Passo a passo instalacao Laravel
---

## **1. Instalar o XAMPP (Servidor Local com MySQL e PHP)**  
O XAMPP fornece um ambiente de servidor Apache com MySQL e PHP para rodar seu projeto Laravel localmente.  

### **Passos:**  
1. Baixe o **XAMPP** no site oficial:  
   -> [https://www.apachefriends.org/](https://www.apachefriends.org/)  
2. Instale o XAMPP e escolha a opção para instalar o MySQL e o PHP.  
3. Após a instalação, abra o **Painel de Controle do XAMPP** e inicie:  
   - **Apache** (servidor web)  
   - **MySQL** (banco de dados)  

---

## **2. Instalar o Composer (Gerenciador de Dependências do PHP)**  
O Composer é essencial para instalar e gerenciar pacotes no Laravel.  

### **Passos:**  
1. Baixe o **Composer** no site oficial:  
   👉 [https://getcomposer.org/](https://getcomposer.org/)  
2. Instale o Composer e **verifique se está funcionando** executando no terminal (cmd, PowerShell ou Git Bash):  
   ```sh
   composer -V
   ```  
   Se retornar a versão do Composer, a instalação foi bem-sucedida.

---

## **3. Criar um Novo Projeto Laravel**  
Agora que temos PHP, MySQL e Composer, podemos instalar o Laravel.  

### **Passos:**  
1. **Abra o terminal** e vá para a pasta onde deseja criar o projeto..

2. **Crie o projeto Laravel** com o Composer:  
   ```sh
   composer create-project --prefer-dist laravel/laravel nome-do-projeto "10.*, versao do Laravel EX: 10.."
   ```  
   (Substitua `nome-do-projeto` pelo nome real do seu projeto.)  
3. **Acesse a pasta do projeto:**  
   ```sh
   cd nome-do-projeto
   ```  
4. **Inicie o servidor embutido do Laravel:**  
   ```sh
   php artisan serve
   ```  
   Isso iniciará o servidor local, geralmente acessível em:  
   -> [http://127.0.0.1:8000](http://127.0.0.1:8000)  

---

## **4. Configurar o Banco de Dados no `.env`**  
1. No diretório do projeto, abra o arquivo `.env`.  
2. Edite as configurações do banco de dados para se conectar ao MySQL do XAMPP:  
   ```
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=nome_do_banco
   DB_USERNAME=root
   DB_PASSWORD=
   ```  
   **Dica:** No XAMPP, o usuário padrão do MySQL é `root` e a senha é vazia.  

3. Crie o banco de dados no **phpMyAdmin** (acessível via [http://localhost/phpmyadmin](http://localhost/phpmyadmin)).  

4. Execute as migrations para criar as tabelas:  
   ```sh
   php artisan migrate
   ```

---

## **5. Configurar Permissões (Linux/macOS)**  
Se estiver usando Linux/macOS, ajuste as permissões das pastas de cache e storage:  
```sh
sudo chmod -R 777 storage bootstrap/cache
```

---

## **6. Configurar o Virtual Host no XAMPP (Opcional)**  
Se quiser acessar seu projeto por um domínio personalizado como `http://meuprojeto.local`, configure um Virtual Host:  

1. **Edite o arquivo do Apache:**  
   ```
   C:\xampp\apache\conf\extra\httpd-vhosts.conf
   ```  
   Adicione:  
   ```
   <VirtualHost *:80>
       DocumentRoot "C:/xampp/htdocs/nome-do-projeto/public"
       ServerName meuprojeto.local
   </VirtualHost>
   ```

2. **Edite o arquivo de hosts do Windows:**  
   ```
   C:\Windows\System32\drivers\etc\hosts
   ```  
   Adicione a linha:  
   ```
   127.0.0.1 meuprojeto.local
   ```

3. Reinicie o Apache no XAMPP. Agora, você pode acessar o Laravel em:  
   -> [http://meuprojeto.local](http://meuprojeto.local)  

---

## **7. Testando a Instalação**  
Para verificar se tudo está funcionando, acesse o terminal e execute:  
```sh
php artisan --version
```  
Se mostrar a versão do Laravel, sua instalação foi bem-sucedida. 🎉  

---

