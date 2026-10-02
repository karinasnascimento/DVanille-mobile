# D'Vanille — App Flutter (protótipo de e-commerce de cafeteria)

Protótipo funcional e navegável de e-commerce para a cafeteria boutique
**D'Vanille**, construído em cima do projeto Flutter original (`dvanille_app`).

## Como rodar

```bash
flutter pub get
flutter run
```

Login de demonstração:
- Qualquer e-mail/senha entra como **cliente**.
- Use `admin@dvanille.com` (qualquer senha) para entrar na **área administrativa**.

## Estrutura do projeto

```
lib/
  main.dart                 # rotas e tema
  theme/app_theme.dart       # paleta oficial e ThemeData
  models/models.dart         # Product, Order, Address, User, GiftCard, restrições (15 condições)
  data/mock_data.dart        # catálogo de produtos de exemplo
  state/app_state.dart       # estado global (ChangeNotifier): carrinho, favoritos,
                              # pedidos, endereços, notificações, vale-presente, admin
  widgets/                   # componentes reutilizáveis (DVanilleHeader, ProductCard,
                              # RestrictionChip, NutritionCard, EmptyState, etc.)
  screens/
    auth/                    # login, cadastro, recuperação de senha
    home/                    # shell de navegação + Home
    menu/                    # cardápio, busca, filtros, detalhes do produto
    favorites/                # favoritos
    offers/                  # ofertas, combos, vale-presente
    cart/                    # carrinho, revisar pedido
    checkout/                # entrega, pagamento, confirmação
    orders/                  # meus pedidos, detalhes, rastreamento
    profile/                 # perfil, endereços, restrições, notificações, configurações
    admin/                   # dashboard, produtos, pedidos (área administrativa)
```

## Identidade visual

Paleta oficial preservada em todas as telas:
marrom `#9C8A73`, marrom forte `#7D6D57`, rosa `#EFCECC`, creme `#FFF4E8`, bege `#E1CDB3`.

Assets de marca em `assets/`:
- `logo.3.png` — logo completa (telas institucionais, autenticação, confirmações)
- `1.png` — versão circular/compacta (headers, perfil)
- `lacinho.png` — lacinho decorativo (rodapés, cantos, confirmações)
- `sacola_lacinho.png` — sacola com lacinho decorativo (carrinho vazio)

## Funcionalidades implementadas

- Cardápio com busca, filtro por categoria e pelas **15 restrições alimentares**
  obrigatórias (lógica AND quando múltiplas são selecionadas).
- Detalhes do produto com informações nutricionais, ingredientes, alergênicos e
  aviso de atenção a alergias.
- Favoritos, carrinho, revisão de pedido, entrega (retirada/delivery), pagamento
  (dinheiro com troco, cartão simulado, PIX simulado, carteira digital) e
  confirmação do pedido.
- Meus pedidos, detalhes do pedido e rastreamento com status simulado.
- Perfil, edição de perfil, endereços (CRUD), restrições alimentares do usuário,
  notificações e configurações.
- Ofertas, combos e vale-presente (compra e listagem).
- Área administrativa simulada: dashboard, CRUD de produtos (com restrições e
  informações nutricionais) e gerenciamento de status de pedidos.
- Estados vazios e feedback de ações em todas as listas/fluxos principais.

Este é um protótipo local (sem backend real): todos os dados vivem em memória
durante a sessão do app.
