# Clean Architecture com Strategy e Composite

Estudo de Clean Architecture em SwiftUI com os padrões Strategy e Composite, num catálogo de produtos e categorias.

Estudo · iOS 26 · 2025

## O que faz
- Lista produtos e categorias e permite criar categorias e produtos novos.
- Ordena os produtos por nome, preço crescente ou preço decrescente (Strategy).
- Monta a árvore de categorias a partir de categoria e categoria-pai (Composite).
- Carrega dados iniciais de um JSON embutido no código e guarda tudo com SwiftData.

## Meu papel
Estudo solo. Todos os commits são meus.

## Como foi feito
- Quatro pastas por responsabilidade: `Domain` (entidades, protocolos de repositório e casos de uso), `Data` (modelos SwiftData, repositórios, `Strategies` e `Composite`), `Presentation` (ViewModels e Views) e `Core`.
- Os casos de uso (`ProductUseCases`, `CategoryUseCases`) dependem dos protocolos de repositório, não das classes concretas.
- `DependencyContainer` cria os repositórios e os casos de uso e entrega ao app: injeção de dependência manual.
- `SortStrategy` é um protocolo com três implementações (nome, preço, preço decrescente); o `DependencyContainer` entrega a estratégia escolhida ao repositório de produtos.
- `CategoryNode.swift` define `CategoryComponent`, `CategoryLeaf` e `CategoryComposite`, e um `CategoryTreeBuilder` que liga os filhos aos pais.

## Tecnologias
Swift, SwiftUI e SwiftData.

## Como rodar
1. Abra `CleanArchitecture/CleanArchitecture.xcodeproj` no Xcode.
2. Rode num simulador com iOS 26 ou mais novo.

---
Feito por Cauê Crillanovick · [portfólio](https://cauecarneiro.github.io/portfolio/) · [LinkedIn](https://www.linkedin.com/in/cau%C3%AA-carneiro)
