# SeTakeOwnershipPrivilege

```mermaid
flowchart TD
    A[🚪 Ponto de Entrada<br>Usuário com SeTakeOwnershipPrivilege] --> B{🔍 Fase de Reconhecimento}
    
    B --> C[whoami /priv<br>Verificar privilégios]
    B --> D[Exploração de File Shares<br>Buscar arquivos sensíveis]
    
    C --> E{Privilégio<br>Habilitado?}
    E -->|Não| F[📜 Executar Scripts de Enable<br>Enable-Privilege.ps1]
    E -->|Sim| G[⚡ Privilégio Ativo]
    
    F --> G
    D --> H[🎯 Identificar Alvo<br>cred.txt, web.config, etc]
    
    G --> I{🚀 Fase de Exploração}
    
    I --> J[takeown /f<br>Assumir propriedade do arquivo]
    I --> K[Verificar propriedade atual<br>Get-ACL ou dir /q]
    
    J --> L[✅ Confirmar Mudança<br>Get-ChildItem + Get-ACL]
    
    L --> M{Consegue Ler?}
    M -->|Não| N[icacls /grant<br>Conceder permissões F]
    M -->|Sim| O[📖 Ler Conteúdo]
    
    N --> O
    
    O --> P[💾 Conteúdo Obtido<br>Credenciais, Chaves SSH, etc]
    
    P --> Q{🔄 Fase Pós-Exploração}
    
    Q --> R[⚠️ Reverter Permissões<br>Se possível]
    Q --> S[📋 Documentar no Relatório<br>Incluir apêndice]
    Q --> T[🎯 Escalada de Privilégios<br>Usar credenciais obtidas]
    
    R --> U[🏁 Objetivo Alcançado]
    S --> U
    T --> U
    
    %% Estilos
    classDef recon fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef exploit fill:#ffebee,stroke:#c62828,stroke-width:2px
    classDef post fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef success fill:#e8f5e8,stroke:#2e7d32,stroke-width:2px
    
    class B,C,D,E recon
    class I,J,K,L,M,N,O exploit
    class Q,R,S,T post
    class P,U success
```
