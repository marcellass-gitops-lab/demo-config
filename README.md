Este repositório atua como a **Fonte Única da Verdade (Single Source of Truth)** para os manifestos de infraestrutura e deployment da aplicação `demo-app` no Kubernetes, gerido continuamente via **ArgoCD** e **Kustomize**.

---

## Estrutura de Diretórios

A parametrização de manifestos segue o padrão declarativo de camadas do Kustomize:

```text
.
├── base/                      # Manifestos genéricos e comuns a todos os ambientes
│   ├── deployment.yaml        # Configuração de pods, recursos e sondas (probes)
│   ├── service.yaml           # Exposição de rede via NodePort
│   └── kustomization.yaml     # Agrupador base de recursos
└── overlays/
    └── dev/                   # Customizações específicas do ambiente de desenvolvimento
        └── kustomization.yaml # Sobrescrita de tags de imagem geradas pelo CI
