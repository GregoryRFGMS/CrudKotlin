# Projeto CRUD Simples em Kotlin com Android Studio

Este projeto demonstra uma funcionalidade básica de CRUD (Create, Read, Update, Delete) usando Kotlin e Room database em um aplicativo Android.

## Estrutura do Projeto

- **`UsuarioModel`**: Representa o modelo de dados para um usuário.
- **`UsuarioDao`**: Interface de Objeto de Acesso a Dados (DAO) para operações no banco de dados Room.
- **`UsuarioDataBase`**: Configuração do banco de dados Room e migrações.
- **`MainActivity`**: Atividade principal que demonstra operações de CRUD.

## Funcionalidades

1. **Operação de Inserção**:
   - Insere um novo `UsuarioModel` no banco de dados.

   ```kotlin
   val retornoInsert = usuarioDatabase.insertUser(UsuarioModel().apply {
       this.nome = "Gregory Rodrigues"
       this.idade = 18
   })
   ```

2. **Operação de Seleção**:
   - Recupera todos os registros de `UsuarioModel` do banco de dados.

   ```kotlin
   val retornoSelectMultiplo = usuarioDatabase.getAll() // Retorna todos os registros

   for (item in retornoSelectMultiplo) {
       Log.d("Retorno Múltiplo", "id_usuario: ${item.id_usuario}, nome: ${item.nome}, idade: ${item.idade}")
   }
   ```

3. **Operações de Atualização e Exclusão**:
   - Métodos `updateUser` e `deleteUser` na interface `UsuarioDao` são utilizados para atualizar e excluir registros, respectivamente.

## Como Usar

Para usar este projeto, siga as etapas abaixo:

1. Clone o repositório:

   ```bash
   git clone https://github.com/GregoryRFGMS/CrudKotlin
   ```

2. Abra o projeto no Android Studio.
3. Execute o aplicativo em um dispositivo ou emulador Android.

## Notas Adicionais

- Este projeto utiliza o Android Studio para o desenvolvimento e o Room para persistência de dados.
- Certifique-se de ajustar as configurações do Room conforme necessário, como versão do banco de dados e migrações, no arquivo `UsuarioDataBase.kt`.

---
