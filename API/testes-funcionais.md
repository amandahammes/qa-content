# Testes Funcionais

Swagger: uma das maneiras de documentação da interface da API REST.
Porém essa documentação não basta para uma cobertura de testes pois não está falando em regras de negócio.

Testes Funcionais: validam conformidade dos requisitos nas regras de negócios. 

Ex: Somente um usuário administrador pode registrar novas viagens.
Então o teste funcional deve validar se essa regra está funcionando conforme o esperado.

As entradas para testar esse exemplo: Credencial (Administrador, Usuário e o que mais?) 
Técnica de partição (ou classes) de equivalência: onde administrador e usuário são partições da entrada credencial.
