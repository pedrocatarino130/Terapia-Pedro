# 📊 Documentação de Analytics - Meu Espaço Terapêutico DBT

## Configuração do Google Analytics 4

### Setup Inicial

1. Acesse [Google Analytics](https://analytics.google.com)
2. Crie uma nova propriedade (Admin → Create Property)
3. Configure um Data Stream para Web
4. Copie o **Measurement ID** (formato: `G-XXXXXXXXXX`)
5. Substitua o ID placeholder no arquivo `index.html` (linha 11 e 18)

### LGPD Compliance

O script está configurado com:
- `anonymize_ip: true` - Anonimiza IPs dos usuários
- `cookie_flags: 'SameSite=None;Secure'` - Cookies seguros
- Opt-out disponível nas configurações (TODO: implementar TASK-038)

---

## 📋 Eventos Customizados Implementados

### 1. `registro_humor`
**Descrição:** Disparado quando o usuário registra seu humor (quick ou detailed)

**Propriedades:**
```javascript
{
  valor_humor: number,      // 1-5 (escala de humor)
  tipo_registro: string,    // "quick" ou "detailed"
  com_nota: boolean,        // (apenas detailed) Se incluiu nota textual
  timestamp: string         // ISO 8601 timestamp
}
```

**Onde:**
- `saveMoodQuick()` - linha ~2052
- `saveMood()` - linha ~2096

**Meta de Sucesso:** Média de 3+ registros/usuário/semana

---

### 2. `exportacao_pdf`
**Descrição:** Disparado quando relatório PDF é gerado com sucesso

**Propriedades:**
```javascript
{
  periodo_selecionado: string,      // "7_dias", "30_dias", etc
  total_registros_humor: number,    // Registros incluídos no período
  total_emocoes: number,            // Emoções incluídas
  total_praticas: number,           // Práticas de mindfulness
  timestamp: string
}
```

**Onde:** `exportPDF()` - linha ~2705

**Meta de Sucesso:** 40%+ dos usuários ativos exportam PDF pelo menos 1x/mês

---

### 3. `pratica_mindfulness`
**Descrição:** Disparado ao registrar prática de mindfulness

**Propriedades:**
```javascript
{
  tipo_pratica: string,       // "Meditação", "Respiração", etc
  duracao_minutos: number,    // Duração da prática
  com_notas: boolean,         // Se incluiu notas
  timestamp: string
}
```

**Onde:** `savePractice()` - linha ~2182

**Meta de Sucesso:** 30%+ dos usuários ativos praticam pelo menos 2x/semana

---

### 4. `visualizacao_insight`
**Descrição:** Disparado quando insight semanal é renderizado no dashboard

**Propriedades:**
```javascript
{
  tipo_insight: string,    // "positive", "support", "neutral"
  emoji: string,           // Emoji do insight
  timestamp: string
}
```

**Onde:** `renderWeeklyInsight()` - linha ~1644

**Meta de Sucesso:** 80%+ dos usuários visualizam insights gerados

---

## 🚧 Eventos a Implementar (Próximas Ondas)

### 5. `conclusao_onboarding`
**Status:** PENDENTE - TASK-008

**Propriedades esperadas:**
```javascript
{
  etapa_final: number,      // 1, 2 ou 3
  tempo_total: number,      // Segundos até conclusão
  pulou: boolean,           // Se pulou o tutorial
  timestamp: string
}
```

---

### 6. `onboarding_iniciado`
**Status:** PENDENTE - TASK-008

**Propriedades esperadas:**
```javascript
{
  timestamp: string
}
```

---

### 7. `ativacao_lembrete`
**Status:** PENDENTE - TASK-014

**Propriedades esperadas:**
```javascript
{
  horario_escolhido: string,  // "08:00", "20:00", etc
  email_fornecido: boolean,
  timestamp: string
}
```

---

## 📈 Dashboards e Relatórios

### Métricas-Chave a Monitorar

| Métrica | Cálculo | Meta MVP |
|---------|---------|----------|
| **WAU** (Weekly Active Users) | Usuários únicos com 3+ registros/semana | 100 usuários |
| **Retenção D7** | % usuários que voltam no dia 7 | >30% |
| **Frequência de Registro** | Média de registros/usuário/semana | 3-5x |
| **Taxa de Exportação PDF** | % que exportam 1+ PDF/mês | >40% |
| **Taxa de Conclusão Onboarding** | % que completam 3 etapas | >70% |

### Visualizações Recomendadas no GA4

1. **Funil de Onboarding:**
   - `onboarding_iniciado` → `onboarding_step_1_completo` → `onboarding_step_2_visualizado` → `onboarding_step_3_completo`

2. **Engajamento Semanal:**
   - Contagem de `registro_humor` por usuário por semana
   - Gráfico de tendência ao longo do tempo

3. **Uso de Features:**
   - % de usuários que usam cada feature (PDF, mindfulness, insights)

4. **Cohort Analysis:**
   - Agrupar usuários por data de cadastro
   - Medir retenção por cohort

---

## 🔍 Como Testar

### Modo de Desenvolvimento

Os eventos são logados no console com prefixo `📊 Analytics Event:` mesmo sem ID do GA4 configurado.

### Teste Manual

1. Abra o DevTools (F12) → Console
2. Execute ações no app (registrar humor, exportar PDF, etc)
3. Verifique logs: `📊 Analytics Event: registro_humor {...}`

### Verificar no GA4 Realtime

1. Acesse GA4 → Reports → Realtime
2. Execute ações no app
3. Eventos devem aparecer em ~10 segundos

---

## 🚨 Troubleshooting

**Eventos não aparecem no GA4:**
- Verificar se Measurement ID está correto (sem espaços)
- Checar se script carregou: `typeof gtag` deve retornar `"function"`
- Verificar se ad blockers estão ativos
- Aguardar até 24h para dados aparecerem em relatórios padrão (Realtime é imediato)

**Erros no Console:**
- Se `gtag is not defined`: Script do GA4 não carregou (bloqueado ou ID inválido)
- Se `trackEvent is not defined`: Função helper não foi definida (verificar linha 24)

---

## 📚 Recursos Adicionais

- [GA4 Event Parameters](https://developers.google.com/analytics/devguides/collection/ga4/event-parameters)
- [LGPD e Google Analytics](https://support.google.com/analytics/answer/9019185)
- [Debug Mode do GA4](https://support.google.com/analytics/answer/7201382)

---

**Última atualização:** TASK-001 concluída - ONDA 0
**Próximos eventos:** TASK-008 (onboarding), TASK-014 (lembretes)
