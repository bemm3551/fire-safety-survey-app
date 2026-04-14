# Design da Aplicação - Levantamento de Equipamentos de Segurança contra Incêndio

## Visão Geral

Aplicação mobile profissional para levantamento rápido de equipamentos de segurança contra incêndio em contexto de inspeção no terreno. Design minimalista, otimizado para uso com uma mão, com foco em contagem rápida e registo de evidências.

---

## Especificações de Design

### Orientação e Dimensões
- **Orientação**: Portrait (9:16)
- **Uso com uma mão**: Todos os botões acessíveis na metade inferior do ecrã
- **Plataformas**: iOS (SafeArea com notch) e Android (edge-to-edge)

### Paleta de Cores

| Elemento | Cor | Uso |
|----------|-----|-----|
| **Primária** | #0A7EA4 (Azul Proteção Civil) | Botões principais, destaques |
| **Secundária** | #FF9500 (Laranja) | Botões de ação secundária |
| **Sucesso** | #22C55E (Verde) | Confirmações, estados positivos |
| **Fundo** | #FFFFFF (Branco) | Fundo principal |
| **Superfície** | #F5F5F5 (Cinzento claro) | Cards, áreas elevadas |
| **Texto Primário** | #11181C (Cinzento escuro) | Texto principal |
| **Texto Secundário** | #687076 (Cinzento médio) | Subtítulos, labels |
| **Borda** | #E5E7EB (Cinzento muito claro) | Divisórias, bordas |

### Tipografia
- **Título Principal**: 28px, Bold, #11181C
- **Subtítulo**: 16px, Regular, #687076
- **Botão**: 16px, Semibold, #FFFFFF (em fundo azul)
- **Contador**: 24px, Bold, #0A7EA4
- **Label de Botão**: 14px, Semibold

---

## Ecrãs da Aplicação

### 1. **Ecrã Principal - Levantamento Ativo** (Home)

#### Conteúdo Principal
- **Cabeçalho**: Logótipo da Proteção Civil de Santo Tirso (topo, 80x80px)
- **Título**: "Levantamento de Equipamentos"
- **Subtítulo**: Data e hora atuais, nome do local (se preenchido)

#### Secção de Contadores (Grid 2 colunas)
Cada contador é um card com:
- **Ícone**: 32x32px, representativo do equipamento
- **Nome**: Texto em português (14px)
- **Valor**: Número grande (24px, azul)
- **Botões**: 
  - Botão "+" (incrementar) - verde/azul, 44x44px
  - Botão "-" (decrementar) - cinzento, 44x44px

**Equipamentos (10 contadores)**:
1. Pó (ícone extintor)
2. CO₂ 2kg (ícone extintor)
3. CO₂ 5kg (ícone extintor)
4. Carretel (ícone mangueira)
5. Carretel Tipo Teatro (ícone mangueira)
6. Manta (ícone manta)
7. Portas Corta-Fogo (ícone porta)
8. Bloco Permanente (ícone sistema)
9. Bloco Não Permanente (ícone sistema)
10. Controlo de Fumo (ícone ventilação)

#### Secção de Ações (Rodapé)
- **Botão "Desfazer"**: Reverter última ação (cinzento, 100% largura)
- **Botão "Fotos"**: Aceder a captura/galeria (azul, 48% largura)
- **Botão "Notas"**: Abrir editor de notas (azul, 48% largura)
- **Botão "Guardar Levantamento"**: Finalizar e guardar (verde, 100% largura)

---

### 2. **Modal/Sheet - Captura de Fotos**

#### Funcionalidade
- Botão "Tirar Foto" (acesso à câmara)
- Botão "Galeria" (selecionar da biblioteca)
- Lista de fotos capturadas (thumbnails 80x80px)
- Botão "Eliminar" para cada foto
- Botão "Fechar" ou "Voltar"

---

### 3. **Modal/Sheet - Editor de Notas**

#### Funcionalidade
- Campo de texto grande (TextInput multiline)
- Placeholder: "Adicione observações sobre o levantamento..."
- Botão "Guardar" (azul)
- Botão "Cancelar" (cinzento)

---

### 4. **Modal - Guardar Levantamento**

#### Funcionalidade
- Campo de entrada: "Nome do Local" (obrigatório)
- Campo de entrada: "Referência/ID" (opcional)
- Data e hora automáticas (apenas leitura)
- Resumo dos contadores (read-only)
- Botão "Confirmar Guardar" (verde)
- Botão "Cancelar" (cinzento)

---

### 5. **Ecrã de Histórico de Levantamentos** (Separador 2)

#### Conteúdo
- Lista de levantamentos guardados (FlatList)
- Cada item mostra:
  - Nome do local
  - Data e hora
  - Número total de equipamentos
  - Botão "Ver Detalhes" (ícone seta)

#### Ações
- Botão "Exportar para Excel" (topo, laranja)
- Botão "Eliminar" (swipe ou ícone, vermelho)

---

### 6. **Ecrã de Detalhes do Levantamento** (Navegação)

#### Conteúdo
- Cabeçalho com nome do local e data
- Tabela com todos os contadores e valores
- Secção de notas
- Galeria de fotos (thumbnails)
- Botão "Voltar"

---

## Fluxos de Utilizador Principais

### Fluxo 1: Levantamento Rápido (Caso de Uso Primário)
1. Utilizador abre a app
2. Vê o ecrã principal com 10 contadores a 0
3. Toca nos botões "+" para incrementar cada equipamento
4. Toca "Desfazer" se cometer erro
5. Toca "Fotos" para capturar evidências
6. Toca "Notas" para adicionar observações
7. Toca "Guardar Levantamento"
8. Preenche nome do local
9. Confirma e levantamento é guardado

### Fluxo 2: Revisão de Levantamentos
1. Utilizador vai ao separador "Histórico"
2. Vê lista de levantamentos anteriores
3. Toca num levantamento para ver detalhes
4. Pode exportar todos para Excel

### Fluxo 3: Exportação para Excel
1. Utilizador vai ao separador "Histórico"
2. Toca "Exportar para Excel"
3. Ficheiro .xlsx é gerado e guardado
4. Opção de partilhar ou enviar por email

---

## Componentes Reutilizáveis

### CounterCard
- Props: `label`, `icon`, `value`, `onIncrement`, `onDecrement`
- Renderiza um card com contador e botões +/-

### ActionButton
- Props: `label`, `onPress`, `variant` (primary/secondary/danger), `size` (small/medium/large)
- Renderiza botão com feedback visual

### PhotoGallery
- Props: `photos`, `onAddPhoto`, `onDeletePhoto`
- Renderiza galeria de fotos com opções

### SurveyCard
- Props: `survey`, `onPress`, `onDelete`
- Renderiza card de levantamento no histórico

---

## Padrões de Interação

### Feedback Visual
- **Botão Pressionado**: Scale 0.97, opacity 0.9
- **Haptic Feedback**: Light impact ao tocar botões principais
- **Toast/Alert**: Confirmação ao guardar levantamento

### Validação
- **Nome do Local**: Obrigatório ao guardar
- **Contadores**: Podem ser 0
- **Fotos**: Opcionais
- **Notas**: Opcionais

### Persistência
- Levantamentos guardados em AsyncStorage (local)
- Fotos guardadas em FileSystem
- Dados sincronizados com backend (se disponível)

---

## Considerações de Acessibilidade

- Botões com tamanho mínimo 44x44px (iOS) / 48x48dp (Android)
- Contraste de cores ≥ 4.5:1 para texto
- Labels descritivos para todos os botões
- Suporte a Dark Mode (automático via tema)

---

## Notas Técnicas

- Usar NativeWind (Tailwind CSS) para styling
- Ícones: Usar MaterialIcons (Android/Web) e SF Symbols (iOS)
- Armazenamento: AsyncStorage para dados, FileSystem para fotos
- Exportação: Usar `xlsx` package para gerar ficheiros Excel
- Câmara: Usar `expo-image-picker` para captura e seleção
- Partilha: Usar `expo-sharing` para enviar ficheiros

