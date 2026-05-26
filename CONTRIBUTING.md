# Guia de Contribuição — vNEXX 🚀

Em primeiro lugar, obrigado por considerar contribuir para o **vNEXX**! 

Acreditamos que democratizar a automação corporativa multimodal não é apenas desenvolver software, é uma verdadeira ação de revolução cognitiva. Ao abrir este código sob a licença MIT, nosso objetivo é construir um padrão global onde inteligência artificial, interação por voz e segurança caminhem juntos de forma acessível e escalável.

Este documento estabelece as diretrizes para garantir que nossa comunidade seja colaborativa, organizada e tecnicamente rigorosa.

## 🛡️ Filosofia Central: Zero Trust
Ao contribuir para o núcleo do sistema (especialmente camadas como o **RunID** ou o **Motor de Intenções/DAG**), lembre-se sempre do princípio de **zero trust** (confiança zero). Nenhuma entrada de usuário, API externa ou executor de tarefas deve ser considerado seguro por padrão. Toda execução deve possuir tokens efêmeros, escopo mínimo e trilha imutável.

---

## 🛠️ Como Contribuir

Existem várias formas de ajudar o ecossistema vNEXX a crescer:

### 1. Reportando Bugs e Solicitando Funcionalidades
* Verifique se o bug ou a ideia já não foi relatada na aba de [Issues](../../issues).
* Caso não encontre, abra uma nova Issue. Seja o mais detalhado possível: inclua passos para reproduzir o erro, logs relevantes e qual era o comportamento esperado.

### 2. Contribuindo com Código
Se você deseja colocar a mão na massa, siga este fluxo de trabalho:

1. **Faça um Fork** do repositório para a sua conta.
2. **Crie uma Branch** para a sua funcionalidade ou correção:
   ```bash
   git checkout -b feature/minha-nova-funcionalidade
   # ou
   git checkout -b fix/correcao-bug-runid

3. Desenvolva seguindo as boas práticas da arquitetura detalhada no README.md (respeite a separação entre RunID, TGhosT, DAG e Data Lakehouse).

4. Faça o Commit de suas alterações. Recomendamos o padrão Conventional Commits:

git commit -m "feat(tghost): adiciona suporte para dialetos regionais do nordeste"
git commit -m "fix(runid): corrige expiração prematura de token no cofre de segredos"

5. Faça o Push para a sua branch:

git push origin feature/minha-nova-funcionalidade
6. Abra um Pull Request (PR) detalhando o que foi feito, qual Issue ele resolve e os testes que foram executados.

📐 Padrões de Código e Arquitetura
Para manter a base de código do vNEXX sustentável:

Mantenha o Modularidade: O sistema é multi-tenant e agnóstico de nuvem. Evite acoplamento forte com fornecedores específicos (ex: AWS, GCP) a menos que seja um módulo específico do marketplace.

Multimodalidade First: Lembre-se que ~90% da interação é feita por voz natural. As respostas da API e do DAG devem ser limpas o suficiente para serem sintetizadas pelo TGhosT de forma audível e agradável.

Testes: Todo novo módulo ou correção crítica deve vir acompanhado de testes unitários ou de integração apropriados.

⚖️ Acordo de Contribuição e Propriedade Intelectual
O vNEXX possui sua arquitetura protegida por patente nacional (BR 10 2025 019674 3), distribuída como uma patente defensiva para garantir que a tecnologia permaneça livre e aberta.

Ao submeter um Pull Request, você concorda que:

1. Suas contribuições serão licenciadas sob a Licença MIT do repositório.

2. Você possui os direitos necessários para submeter o código.

3. Suas adições alinham-se à missão de manter o vNEXX como um padrão aberto, respeitando a propriedade intelectual matriz da RunAI Systems Limited Liability Company.

Bem-vindo à equipe. Vamos construir o futuro da automação juntos!
