# Levantamento de Equipamentos de Segurança - TODO

## Funcionalidades Obrigatórias

### Ecrã Principal - Contadores
- [x] Implementar layout grid 2 colunas para 10 contadores
- [x] Criar componente CounterCard com ícone, nome e valor
- [x] Implementar botão "+" para incrementar contador
- [x] Implementar botão "-" para decrementar contador
- [x] Adicionar feedback visual (scale, opacity) ao pressionar botões
- [x] Adicionar haptic feedback ao incrementar
- [x] Implementar histórico de ações para desfazer
- [x] Criar botão "Desfazer" funcional

### Equipamentos (Contadores)
- [x] Pó (ícone extintor)
- [x] CO₂ 2kg (ícone extintor)
- [x] CO₂ 5kg (ícone extintor)
- [x] Carretel (ícone mangueira)
- [x] Carretel Tipo Teatro (ícone mangueira)
- [x] Manta (ícone manta)
- [x] Portas Corta-Fogo (ícone porta)
- [x] Bloco Permanente (ícone sistema)
- [x] Bloco Não Permanente (ícone sistema)
- [x] Controlo de Fumo (ícone ventilação)

### Funcionalidades de Fotos
- [x] Implementar botão "Fotos" no ecrã principal
- [x] Criar modal/sheet para captura de fotos
- [x] Integrar expo-image-picker para câmara
- [x] Integrar expo-image-picker para galeria
- [x] Guardar fotos no FileSystem
- [x] Mostrar galeria de fotos capturadas
- [x] Permitir eliminar fotos
- [x] Associar fotos ao levantamento atual

### Funcionalidades de Notas
- [x] Implementar botão "Notas" no ecrã principal
- [x] Criar modal/sheet para editor de notas
- [x] Implementar TextInput multiline
- [x] Guardar notas no estado local
- [x] Persistir notas ao guardar levantamento

### Guardar Levantamento
- [x] Criar modal para confirmação de guardar
- [x] Campo de entrada "Nome do Local" (obrigatório)
- [x] Campo de entrada "Referência/ID" (opcional)
- [x] Data e hora automáticas
- [x] Validar nome do local
- [x] Guardar levantamento em AsyncStorage
- [x] Guardar fotos associadas
- [x] Guardar notas associadas
- [x] Limpar contadores após guardar

### Ecrã de Histórico
- [x] Criar separador "Histórico" na tab bar
- [x] Implementar FlatList de levantamentos guardados
- [x] Mostrar nome do local, data, total de equipamentos
- [ ] Implementar botão "Ver Detalhes"
- [x] Implementar botão "Eliminar" (swipe ou ícone)
- [x] Carregar levantamentos do AsyncStorage

### Ecrã de Detalhes do Levantamento
- [ ] Criar ecrã de detalhes
- [ ] Mostrar informações do levantamento (local, data)
- [ ] Mostrar tabela com todos os contadores e valores
- [ ] Mostrar secção de notas
- [ ] Mostrar galeria de fotos
- [ ] Implementar navegação de volta

### Exportação para Excel
- [x] Implementar botão "Exportar para Excel" no histórico
- [x] Instalar package `xlsx`
- [x] Criar função para gerar ficheiro Excel
- [x] Incluir colunas: Local, Data, Pó, CO₂ 2kg, CO₂ 5kg, Carretel, Carretel Tipo Teatro, Manta, Portas Corta-Fogo, Bloco Permanente, Bloco Não Permanente, Controlo de Fumo, Notas
- [x] Incluir referências de fotos no Excel
- [x] Guardar ficheiro no FileSystem
- [x] Permitir partilhar ficheiro

### Identidade Visual
- [x] Guardar logótipo da Proteção Civil de Santo Tirso
- [x] Mostrar logótipo no topo do ecrã principal
- [ ] Mostrar logótipo no ecrã de detalhes/relatório
- [ ] Aplicar paleta de cores (azul #0A7EA4, laranja #FF9500)
- [ ] Atualizar app.config.ts com nome e branding

### UI/UX Polimento
- [ ] Implementar tema claro/escuro
- [ ] Adicionar animações sutis (fade-in, scale)
- [ ] Otimizar layout para diferentes tamanhos de ecrã
- [ ] Adicionar loading indicators
- [ ] Adicionar error handling
- [ ] Testar em iOS e Android
- [ ] Testar com Expo Go

## Funcionalidades Opcionais

- [ ] Sincronização com backend (cloud)
- [ ] Autenticação de utilizador
- [ ] Histórico de sincronização
- [ ] Busca/filtro de levantamentos
- [ ] Estatísticas/relatórios
- [ ] Impressão de relatórios
- [ ] Suporte offline completo

## Bugs Conhecidos

(Nenhum no momento)

## Notas Técnicas

- Usar NativeWind para styling (Tailwind CSS)
- Usar MaterialIcons para ícones (Android/Web)
- Usar AsyncStorage para persistência local
- Usar FileSystem para guardar fotos
- Usar expo-image-picker para câmara/galeria
- Usar xlsx para exportação Excel
- Usar expo-sharing para partilhar ficheiros



## Alterações Solicitadas (Fase 7)

### Novos Equipamentos
- [x] Adicionar contador CDI
- [x] Adicionar contador Sirene
- [x] Adicionar contador Botão de alarme
- [x] Adicionar contador Detetores

### Renomeações
- [x] Renomear "Carretel" para "BIATC"
- [x] Renomear "Carretel Tipo Teatro" para "BIATT"

### Campo de Instalação
- [x] Adicionar campo de texto para nome da instalação no ecrã principal
- [x] Guardar nome da instalação com o levantamento
- [x] Mostrar nome da instalação no histórico
- [x] Incluir nome da instalação na exportação para Excel


## Suporte Web para PC

### Layout Responsivo
- [x] Adaptar layout para desktop (telas maiores que 1024px)
- [x] Criar layout em grid 3-4 colunas para contadores em desktop
- [x] Ajustar tamanhos de fonte e botões para desktop
- [x] Otimizar espaçamento para telas grandes

### Interações Web
- [x] Adicionar suporte a teclado (Tab, Enter, Escape)
- [x] Otimizar para mouse (hover states, cursores)
- [ ] Adicionar atalhos de teclado (Ctrl+S para guardar, etc)
- [ ] Melhorar acessibilidade (ARIA labels, semantic HTML)

### Funcionalidades Web
- [ ] Permitir upload de fotos via drag-and-drop
- [x] Suporte a múltiplas seleções de fotos
- [x] Exportação para Excel otimizada para web
- [ ] Impressão de relatórios (Print CSS)

### Testes Web
- [ ] Testar em Chrome
- [ ] Testar em Firefox
- [ ] Testar em Safari
- [ ] Testar em Edge
- [ ] Validar responsividade em diferentes resoluções


## Alterações Recentes (Fase 8)

- [x] Alterar layout dos equipamentos de grid para lista vertical
- [x] Remover responsividade de colunas (manter sempre 1 coluna)
- [x] Otimizar altura dos cards para lista


## Organização de Fotos por Instalação (Fase 9)

- [x] Criar pasta com nome da instalação + data
- [x] Guardar fotos numeradas (foto_001.jpg, foto_002.jpg, etc.)
- [x] Criar estrutura de pastas com Excel + pastas de fotos
- [x] Adicionar informação de fotos no Excel (nome da pasta, quantidade)
- [x] Permitir partilha da pasta de exportação
- [x] Atualizar tipos TypeScript (ExportData)


## Correção de Exportação (Fase 10)

- [x] Instalar biblioteca de ZIP (jszip)
- [x] Criar ficheiro ZIP com Excel + pastas de fotos
- [x] Partilhar ficheiro ZIP em vez de pasta
- [x] Testar partilha por email


## Correção do Histórico (Fase 11)

- [x] Investigar loop infinito no carregamento do histórico
- [x] Corrigir useEffect no ecrã de histórico
- [x] Testar carregamento de levantamentos guardados
- [x] Verificar performance com múltiplos levantamentos


## Correção de Web (Fase 12)

- [x] Desabilitar câmara em web (apenas galeria disponível)
- [x] Adicionar tratamento de erros melhorado
- [x] Verificar permissões por plataforma
- [x] Testar no navegador Safari


## Deploy Permanente no GitHub Pages (Fase 13)

- [x] Preparar código para GitHub
- [x] Criar ZIP com código
- [x] Criar instruções para upload
- [ ] Upload dos ficheiros no GitHub
- [ ] Ativar GitHub Pages nas definições
- [ ] Testar app no domínio final (https://bemm3551.github.io/fire-safety-survey-app/)
