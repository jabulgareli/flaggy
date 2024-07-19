## Flaggy: Seu Gerenciador de Feature Flags Open-Source em .NET Core

**Flaggy** é um projeto **open-source** de **feature flags as a service** em **.NET Core** que facilita o gerenciamento de recursos em seus aplicativos. Com o Flaggy, você pode:

* **Obter o status de uma flag:** Verifique se uma flag está ativa ou desativada para um determinado tenant e conjunto de parâmetros personalizados (por exemplo, `userId=x, foo=bar`) usando uma requisição HTTP simples.
* **Receber atualizações de flags em tempo real:** Assine um websocket para receber notificações instantâneas sobre alterações nas flags, garantindo que seus aplicativos estejam sempre atualizados.
* **Implementar lançamentos de flags com controle granular:**
    * **Liberação gradual por lista de tenant:** Libere recursos para um conjunto específico de tenants, ideal para testes A/B e lançamentos controlados.
    * **Liberação gradual por percentual da base:** Libere recursos para uma porcentagem da sua base de usuários, aumentando gradativamente a disponibilidade à medida que coleta dados e feedback.
    * **Liberação binária:** Ative ou desative instantaneamente um recurso para toda a sua base de usuários.
* **Desfrute de um SDK .NET completo:** O Flaggy oferece um SDK .NET robusto para facilitar a integração com seus aplicativos.

## Exemplo de Utilização em C#

```c#
using FlaggyClient;

// Crie um cliente Flaggy
var client = new FlaggyClient("https://your-flaggy-instance.com");

// Verifique se a flag "new-feature" está ativa para o tenant "tenant1" e o usuário "user123"
var isFeatureActive = await client.IsFlagActiveAsync("new-feature", "tenant1", new Dictionary<string, string> { { "userId", "user123" } });

if (isFeatureActive)
{
    // Ative o novo recurso para o usuário
    Console.WriteLine("Novo recurso ativado para user123!");
}
else
{
    // Desative o novo recurso para o usuário
    Console.WriteLine("Novo recurso desativado para user123.");
}
```

## Benefícios do Flaggy

**Flaggy** oferece diversos benefícios para o desenvolvimento de software:

* **Agilidade:** Libere recursos com mais rapidez e segurança, sem a necessidade de deployments frequentes.
* **Confiabilidade:** Reduza o risco de bugs e falhas ao testar recursos em grupos menores de usuários antes do lançamento geral.
* **Experimentação:** Realize testes A/B e compare o desempenho de diferentes versões de recursos para tomar decisões informadas.
* **Controle:** Gerencie o acesso a recursos com granularidade, liberando-os para grupos específicos de usuários ou porcentagens da base.

## Comece a usar o Flaggy hoje mesmo!

* **Repositório GitHub:** [https://github.com/jabulgareli/flaggy]([https://es.wiktionary.org/wiki/removido](https://github.com/jabulgareli/flaggy))
  
**Flaggy:** O futuro do gerenciamento de feature flags em .NET Core.
