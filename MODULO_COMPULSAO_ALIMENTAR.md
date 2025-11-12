# 🍽️ Módulo de Compulsão Alimentar - Especificação Técnica

## 📋 Contexto da Sessão de Terapia

**Data:** 11/11/2025
**Terapeuta:** Psicóloga DBT
**Foco:** Tratamento de compulsão alimentar com técnicas DBT

---

## 🎯 Conceitos-Chave da Sessão

### 1. **Natureza da Compulsão Alimentar**
- ❌ **NÃO é** falta de força de vontade
- ✅ **É** comportamento aprendido e mantido por:
  - Reforços biológicos (comidas hiperpalatáveis ativam hormônios de prazer)
  - Reforços emocionais (alívio temporário de emoções negativas)

### 2. **Ciclo da Compulsão** (5 Estágios)

```
1. GATILHO EMOCIONAL
   ↓ (Estresse, tristeza, ansiedade, medo, solidão)

2. SENSAÇÕES INTERNAS DESCONFORTÁVEIS
   ↓ (Desconforto físico, vontade de chorar, mal-estar)

3. COMPORTAMENTO DE COMER
   ↓ (Alívio momentâneo - Reforço negativo)

4. EMOÇÕES SECUNDÁRIAS
   ↓ (Culpa, vergonha, arrependimento)

5. RETORNO DAS EMOÇÕES DESAGRADÁVEIS
   ↓ (Volta ao estágio 1 - Mantém o ciclo)
```

### 3. **O que Piora a Compulsão**
- ⚠️ Dietas muito rígidas
- ⚠️ Restrição calórica severa
- ⚠️ Promessas de controle ("amanhã não como nada")
- ⚠️ Comportamentos compensatórios (purgação, exercício excessivo)
- ⚠️ Autocrítica e culpa

### 4. **Tratamento DBT para Compulsão**

#### 📊 **Fase 1: Auto-Monitoramento**
**Diário Alimentar Emocional** - Registrar:
- **Antes de comer:** Emoções presentes, intensidade, gatilhos
- **Durante:** Como comeu (rápido/devagar), local, companhia
- **Depois:** O que comeu, quantidade, consequências emocionais

**Objetivo:** Mapear padrões de comportamento

#### 🧘 **Fase 2: Regulação Emocional**
Técnicas baseadas na intensidade da emoção:

**Emoções INTENSAS (8-10/10):**
- 🧊 **TIPP** (Temperature, Intense exercise, Paced breathing, Progressive relaxation)

**Emoções MODERADAS (4-7/10):**
- 🏃 **ACCEPTS** (Atividade física + atenção plena)
- 🫁 Respiração diafragmática
- 🌍 Grounding (técnicas de ancoragem)
- 📝 RPD (Registro de Pensamentos Disfuncionais)

#### 🔄 **Fase 3: Substituição de Comportamento**
- Trocar comportamento disfuncional (comer compulsivamente) por funcional
- **Alimentos estratégicos** para saciedade:
  - 🥚 Proteínas (saciam mais e por mais tempo)
  - 🌾 Fibras (incham no intestino - aveia, chia, linhaça)
  - 💧 Água (hidratação adequada)

#### 📈 **Fase 4: Progressão Gradual**
- Não é processo rápido nem linear
- Redução gradual de episódios
- Comemorar pequenas vitórias

---

## 🚀 Funcionalidades a Implementar

### **M13: Módulo Completo de Compulsão Alimentar**

#### 🔴 **Prioridade: CRÍTICA** (baseado na sessão de terapia)

---

### 📝 **13.1: Diário Alimentar Emocional**

#### **Interface de Registro**

```html
<div id="foodCompulsion" class="tab-content">
  <h2>🍽️ Diário Alimentar Emocional</h2>

  <!-- Explicação do ciclo -->
  <div class="info-card">
    <h3>📚 Sobre Compulsão Alimentar</h3>
    <p>A compulsão não é falta de vontade. É um comportamento mantido por reforços
    biológicos e emocionais. Este diário ajuda a mapear seu ciclo pessoal.</p>
  </div>

  <!-- Formulário de Registro -->
  <div class="dashboard-card">
    <h3>Registrar Episódio</h3>

    <!-- ANTES DE COMER -->
    <div class="form-section">
      <h4>1️⃣ Antes de Comer</h4>

      <div class="form-group">
        <label>Emoções presentes (selecione todas que sentiu)</label>
        <div class="emotion-checkboxes">
          <label><input type="checkbox" value="Ansiedade"> Ansiedade</label>
          <label><input type="checkbox" value="Tristeza"> Tristeza</label>
          <label><input type="checkbox" value="Estresse"> Estresse</label>
          <label><input type="checkbox" value="Solidão"> Solidão</label>
          <label><input type="checkbox" value="Medo"> Medo</label>
          <label><input type="checkbox" value="Tédio"> Tédio</label>
          <label><input type="checkbox" value="Raiva"> Raiva</label>
          <label><input type="checkbox" value="Outra"> Outra</label>
        </div>
      </div>

      <div class="form-group">
        <label>Intensidade Emocional</label>
        <input type="range" id="emotionIntensityBefore" min="0" max="10" value="5">
        <span id="intensityValueBefore">5/10</span>
      </div>

      <div class="form-group">
        <label>Gatilho identificado (opcional)</label>
        <textarea id="trigger" placeholder="O que aconteceu antes? Ex: briga, notícia ruim, situação estressante..."></textarea>
      </div>

      <div class="form-group">
        <label>Sensações físicas</label>
        <textarea id="physicalSensations" placeholder="Ex: aperto no peito, tremor, tensão muscular, vontade de chorar..."></textarea>
      </div>
    </div>

    <!-- DURANTE O COMER -->
    <div class="form-section">
      <h4>2️⃣ Durante o Comer</h4>

      <div class="form-group">
        <label>Como você comeu?</label>
        <select id="eatingPace">
          <option value="">Selecione...</option>
          <option value="Muito rápido">Muito rápido (sem perceber)</option>
          <option value="Rápido">Rápido</option>
          <option value="Normal">Normal</option>
          <option value="Devagar">Devagar</option>
          <option value="Mindful">Com atenção plena</option>
        </select>
      </div>

      <div class="form-group">
        <label>Local</label>
        <select id="location">
          <option value="">Selecione...</option>
          <option value="Casa - Cozinha">Casa - Cozinha</option>
          <option value="Casa - Quarto">Casa - Quarto</option>
          <option value="Casa - Sala">Casa - Sala</option>
          <option value="Trabalho">Trabalho</option>
          <option value="Restaurante">Restaurante</option>
          <option value="Evento/Festa">Evento/Festa</option>
          <option value="Carro">Carro</option>
          <option value="Outro">Outro</option>
        </select>
      </div>

      <div class="form-group">
        <label>Companhia</label>
        <select id="company">
          <option value="Sozinho">Sozinho</option>
          <option value="Família">Família</option>
          <option value="Amigos">Amigos</option>
          <option value="Colegas">Colegas</option>
          <option value="Parceiro">Parceiro</option>
        </select>
      </div>

      <div class="form-group">
        <label>Estava fazendo outra coisa enquanto comia?</label>
        <div class="checkbox-group">
          <label><input type="checkbox" value="TV"> Assistindo TV</label>
          <label><input type="checkbox" value="Celular"> Mexendo no celular</label>
          <label><input type="checkbox" value="Trabalho"> Trabalhando</label>
          <label><input type="checkbox" value="Conversa"> Conversando</label>
          <label><input type="checkbox" value="Nada"> Apenas comendo</label>
        </div>
      </div>
    </div>

    <!-- DEPOIS DE COMER -->
    <div class="form-section">
      <h4>3️⃣ Depois de Comer</h4>

      <div class="form-group">
        <label>O que você comeu?</label>
        <textarea id="foodEaten" placeholder="Liste os alimentos e quantidades aproximadas..."></textarea>
      </div>

      <div class="form-group">
        <label>Tipo de alimentos</label>
        <div class="checkbox-group">
          <label><input type="checkbox" value="Doces"> Doces</label>
          <label><input type="checkbox" value="Salgados"> Salgados processados</label>
          <label><input type="checkbox" value="Fast food"> Fast food</label>
          <label><input type="checkbox" value="Bebidas açucaradas"> Bebidas açucaradas</label>
          <label><input type="checkbox" value="Frutas"> Frutas</label>
          <label><input type="checkbox" value="Vegetais"> Vegetais</label>
          <label><input type="checkbox" value="Proteínas"> Proteínas</label>
          <label><input type="checkbox" value="Carboidratos"> Carboidratos</label>
        </div>
      </div>

      <div class="form-group">
        <label>Emoções após comer</label>
        <div class="checkbox-group">
          <label><input type="checkbox" value="Culpa"> Culpa</label>
          <label><input type="checkbox" value="Vergonha"> Vergonha</label>
          <label><input type="checkbox" value="Alívio"> Alívio temporário</label>
          <label><input type="checkbox" value="Arrependimento"> Arrependimento</label>
          <label><input type="checkbox" value="Satisfação"> Satisfação</label>
          <label><input type="checkbox" value="Desconforto físico"> Desconforto físico</label>
          <label><input type="checkbox" value="Neutralidade"> Sem emoção forte</label>
        </div>
      </div>

      <div class="form-group">
        <label>Intensidade Emocional após</label>
        <input type="range" id="emotionIntensityAfter" min="0" max="10" value="5">
        <span id="intensityValueAfter">5/10</span>
      </div>

      <div class="form-group">
        <label>Pensamentos após comer</label>
        <textarea id="thoughtsAfter" placeholder="O que passou pela sua cabeça? Ex: 'Não tenho controle', 'Sou fraco', 'Amanhã vou compensar'..."></textarea>
      </div>

      <div class="form-group">
        <label>Comportamentos compensatórios? (Se houver)</label>
        <div class="checkbox-group">
          <label><input type="checkbox" value="Exercício excessivo"> Planejou exercício excessivo</label>
          <label><input type="checkbox" value="Restrição"> Planejou restrição alimentar</label>
          <label><input type="checkbox" value="Purgação"> Vômito ou laxantes</label>
          <label><input type="checkbox" value="Nenhum"> Nenhum</label>
        </div>
      </div>
    </div>

    <!-- TÉCNICAS USADAS -->
    <div class="form-section">
      <h4>4️⃣ Tentou usar alguma técnica antes de comer?</h4>

      <div class="form-group">
        <label>
          <input type="checkbox" id="usedTechnique">
          Sim, tentei usar técnicas de regulação
        </label>
      </div>

      <div id="techniquesSection" style="display: none;">
        <div class="form-group">
          <label>Quais técnicas?</label>
          <div class="checkbox-group">
            <label><input type="checkbox" value="TIPP"> TIPP</label>
            <label><input type="checkbox" value="ACCEPTS"> ACCEPTS</label>
            <label><input type="checkbox" value="Respiração"> Respiração diafragmática</label>
            <label><input type="checkbox" value="Grounding"> Grounding</label>
            <label><input type="checkbox" value="RPD"> Registro de Pensamentos</label>
            <label><input type="checkbox" value="Distração"> Distração saudável</label>
            <label><input type="checkbox" value="Outra"> Outra</label>
          </div>
        </div>

        <div class="form-group">
          <label>A técnica ajudou?</label>
          <select id="techniqueEffectiveness">
            <option value="Não ajudou">Não ajudou (comeu da mesma forma)</option>
            <option value="Ajudou pouco">Ajudou pouco (comeu menos)</option>
            <option value="Ajudou moderadamente">Ajudou moderadamente (evitou parte da compulsão)</option>
            <option value="Ajudou muito">Ajudou muito (evitou completamente)</option>
          </select>
        </div>
      </div>
    </div>

    <button class="btn btn-primary" onclick="saveFoodCompulsionEntry()">
      💾 Salvar Registro
    </button>
  </div>

  <!-- HISTÓRICO -->
  <h3 style="margin-top: 40px;">📜 Histórico de Episódios</h3>

  <div class="filter-section">
    <select id="compulsionPeriodFilter" onchange="filterCompulsionHistory()">
      <option value="7">Última semana</option>
      <option value="30">Último mês</option>
      <option value="90">Últimos 3 meses</option>
      <option value="all">Todos</option>
    </select>
  </div>

  <div id="compulsionHistory"></div>
</div>
```

#### **Schema de Dados**

```javascript
Schema.FoodCompulsionEntry = {
  create(data) {
    return {
      id: crypto.randomUUID(),

      // Antes de comer
      emotionsBefore: data.emotionsBefore, // Array de strings
      intensityBefore: data.intensityBefore, // 0-10
      trigger: data.trigger,
      physicalSensations: data.physicalSensations,

      // Durante
      eatingPace: data.eatingPace,
      location: data.location,
      company: data.company,
      distractions: data.distractions, // Array

      // Depois
      foodEaten: data.foodEaten,
      foodTypes: data.foodTypes, // Array
      emotionsAfter: data.emotionsAfter, // Array
      intensityAfter: data.intensityAfter, // 0-10
      thoughtsAfter: data.thoughtsAfter,
      compensatoryBehaviors: data.compensatoryBehaviors, // Array

      // Técnicas
      usedTechnique: data.usedTechnique, // boolean
      techniques: data.techniques, // Array (se usou)
      techniqueEffectiveness: data.techniqueEffectiveness, // string

      // Metadata
      timestamp: new Date().toISOString(),
      date: new Date().toISOString().split('T')[0]
    };
  }
};
```

---

### 📊 **13.2: Visualização do Ciclo Pessoal**

#### **Dashboard de Compulsão**

```html
<div class="dashboard-card">
  <h3>🔄 Seu Ciclo de Compulsão</h3>

  <!-- Estatísticas rápidas -->
  <div class="stats-grid">
    <div class="stat-card">
      <h4>Episódios esta semana</h4>
      <p class="stat-value" id="episodesThisWeek">0</p>
      <span class="stat-change" id="episodesTrend"></span>
    </div>

    <div class="stat-card">
      <h4>Gatilhos mais comuns</h4>
      <ul id="topTriggers"></ul>
    </div>

    <div class="stat-card">
      <h4>Técnicas mais efetivas</h4>
      <ul id="effectiveTechniques"></ul>
    </div>
  </div>

  <!-- Visualização do ciclo -->
  <div class="cycle-visualization">
    <h4>Padrões Identificados</h4>
    <canvas id="compulsionCycleChart"></canvas>
  </div>

  <!-- Insights automáticos -->
  <div class="insights-section" id="compulsionInsights">
    <!-- Gerado dinamicamente -->
  </div>
</div>
```

#### **Análises Automáticas**

```javascript
function generateCompulsionInsights(entries) {
  const insights = [];

  // 1. Gatilhos mais frequentes
  const triggerCount = {};
  entries.forEach(e => {
    e.emotionsBefore.forEach(emotion => {
      triggerCount[emotion] = (triggerCount[emotion] || 0) + 1;
    });
  });
  const topTrigger = Object.entries(triggerCount)
    .sort((a, b) => b[1] - a[1])[0];

  if (topTrigger) {
    insights.push({
      type: 'trigger',
      icon: '🎯',
      title: 'Gatilho Principal',
      message: `${topTrigger[0]} aparece em ${topTrigger[1]} de ${entries.length} episódios (${Math.round(topTrigger[1]/entries.length*100)}%)`
    });
  }

  // 2. Horários de risco
  const hourCount = {};
  entries.forEach(e => {
    const hour = new Date(e.timestamp).getHours();
    hourCount[hour] = (hourCount[hour] || 0) + 1;
  });
  const riskHour = Object.entries(hourCount)
    .sort((a, b) => b[1] - a[1])[0];

  if (riskHour) {
    insights.push({
      type: 'time',
      icon: '⏰',
      title: 'Horário de Risco',
      message: `${riskHour[1]} episódios ocorreram por volta das ${riskHour[0]}h. Considere planejar uma técnica de regulação nesse horário.`
    });
  }

  // 3. Efetividade de técnicas
  const withTechniques = entries.filter(e => e.usedTechnique);
  if (withTechniques.length > 0) {
    const helped = withTechniques.filter(e =>
      e.techniqueEffectiveness.includes('Ajudou')
    ).length;
    const rate = Math.round(helped / withTechniques.length * 100);

    insights.push({
      type: 'technique',
      icon: '🧘',
      title: 'Efetividade das Técnicas',
      message: `Quando você usa técnicas de regulação, elas ajudam em ${rate}% dos casos. Continue praticando!`
    });
  }

  // 4. Progressão
  const lastWeek = entries.filter(e => {
    const date = new Date(e.date);
    const weekAgo = new Date();
    weekAgo.setDate(weekAgo.getDate() - 7);
    return date >= weekAgo;
  });

  const prevWeek = entries.filter(e => {
    const date = new Date(e.date);
    const twoWeeksAgo = new Date();
    twoWeeksAgo.setDate(twoWeeksAgo.getDate() - 14);
    const weekAgo = new Date();
    weekAgo.setDate(weekAgo.getDate() - 7);
    return date >= twoWeeksAgo && date < weekAgo;
  });

  if (prevWeek.length > 0) {
    const change = lastWeek.length - prevWeek.length;
    if (change < 0) {
      insights.push({
        type: 'progress',
        icon: '📈',
        title: 'Progresso Positivo',
        message: `Você teve ${Math.abs(change)} episódio(s) a menos esta semana! Continue assim! 🎉`
      });
    } else if (change > 0) {
      insights.push({
        type: 'warning',
        icon: '⚠️',
        title: 'Semana Desafiadora',
        message: `Os episódios aumentaram esta semana. Lembre-se: é um processo gradual. Seja gentil consigo mesmo.`
      });
    }
  }

  return insights;
}
```

---

### 🎓 **13.3: Biblioteca Educacional sobre Compulsão**

```html
<div class="education-section">
  <h3>📚 Entenda a Compulsão Alimentar</h3>

  <div class="accordion">
    <div class="accordion-item">
      <button class="accordion-header">
        🧠 Por que acontece?
      </button>
      <div class="accordion-content">
        <p>A compulsão alimentar NÃO é falta de força de vontade. É um comportamento mantido por:</p>
        <ul>
          <li><strong>Reforços biológicos:</strong> Alimentos hiperpalatáveis (doces, frituras) liberam hormônios de prazer</li>
          <li><strong>Reforços emocionais:</strong> Comer alivia temporariamente emoções negativas (reforço negativo)</li>
        </ul>
      </div>
    </div>

    <div class="accordion-item">
      <button class="accordion-header">
        🔄 O Ciclo da Compulsão
      </button>
      <div class="accordion-content">
        <img src="ciclo-compulsao.svg" alt="Ciclo da Compulsão">
        <ol>
          <li><strong>Gatilho Emocional:</strong> Estresse, ansiedade, tristeza, medo, solidão</li>
          <li><strong>Sensações Desconfortáveis:</strong> Mal-estar físico, vontade de chorar</li>
          <li><strong>Comportamento de Comer:</strong> Alívio momentâneo</li>
          <li><strong>Emoções Secundárias:</strong> Culpa, vergonha</li>
          <li><strong>Retorno:</strong> Volta ao início do ciclo</li>
        </ol>
      </div>
    </div>

    <div class="accordion-item">
      <button class="accordion-header">
        ⚠️ O que NÃO fazer
      </button>
      <div class="accordion-content">
        <ul>
          <li>❌ Dietas muito rígidas ou restritivas</li>
          <li>❌ Promessas de compensação ("amanhã não como nada")</li>
          <li>❌ Comportamentos purgativos (vômito, laxantes, exercício excessivo)</li>
          <li>❌ Autocrítica severa ("sou fraco", "não tenho controle")</li>
        </ul>
        <p><strong>Estes comportamentos pioram a compulsão!</strong></p>
      </div>
    </div>

    <div class="accordion-item">
      <button class="accordion-header">
        ✅ Como trabalhar com isso
      </button>
      <div class="accordion-content">
        <h4>1. Auto-Monitoramento</h4>
        <p>Use este diário para mapear seu ciclo pessoal</p>

        <h4>2. Regulação Emocional</h4>
        <p>Escolha técnicas baseadas na intensidade:</p>
        <ul>
          <li><strong>Emoção intensa (8-10/10):</strong> TIPP</li>
          <li><strong>Emoção moderada (4-7/10):</strong> ACCEPTS, respiração, grounding</li>
        </ul>

        <h4>3. Substituição de Comportamento</h4>
        <p>Alimentos que ajudam na saciedade:</p>
        <ul>
          <li>🥚 Proteínas (ovos, frango, peixe, tofu)</li>
          <li>🌾 Fibras (aveia, chia, linhaça, vegetais)</li>
          <li>💧 Água (pelo menos 2L por dia)</li>
        </ul>

        <h4>4. Processo Gradual</h4>
        <p>Não espere mudanças rápidas. Celebre pequenos progressos!</p>
      </div>
    </div>
  </div>
</div>
```

---

### 🎯 **13.4: Plano de Ação Anti-Compulsão**

```html
<div class="action-plan-card">
  <h3>🛡️ Meu Plano de Ação</h3>

  <div class="plan-section">
    <h4>Quando sentir vontade de comer compulsivamente:</h4>

    <div class="step">
      <span class="step-number">1</span>
      <div class="step-content">
        <h5>PAUSA</h5>
        <p>Pare por 5 minutos antes de comer. Respire fundo.</p>
      </div>
    </div>

    <div class="step">
      <span class="step-number">2</span>
      <div class="step-content">
        <h5>IDENTIFIQUE</h5>
        <p>Qual emoção estou sentindo? (Use o checklist de emoções)</p>
        <button class="btn-small" onclick="quickEmotionCheck()">
          Checagem Rápida
        </button>
      </div>
    </div>

    <div class="step">
      <span class="step-number">3</span>
      <div class="step-content">
        <h5>ESCOLHA UMA TÉCNICA</h5>
        <div id="suggestedTechniques">
          <!-- Gerado baseado na intensidade emocional -->
        </div>
      </div>
    </div>

    <div class="step">
      <span class="step-number">4</span>
      <div class="step-content">
        <h5>REAVALIE</h5>
        <p>Após 10 minutos, ainda sinto vontade?</p>
        <div class="button-group">
          <button class="btn-success" onclick="compulsionAvoided()">
            ✅ Passou a vontade
          </button>
          <button class="btn-secondary" onclick="showHealthyOptions()">
            🍎 Vou comer algo saudável
          </button>
          <button class="btn-warning" onclick="startCompulsionRecord()">
            📝 Vou registrar o episódio
          </button>
        </div>
      </div>
    </div>
  </div>

  <!-- Técnicas rápidas sempre visíveis -->
  <div class="quick-techniques">
    <h4>⚡ Acesso Rápido às Técnicas</h4>
    <div class="technique-buttons">
      <button onclick="showTechnique('tipp')">🧊 TIPP</button>
      <button onclick="showTechnique('accepts')">🏃 ACCEPTS</button>
      <button onclick="showTechnique('breathing')">🫁 Respiração</button>
      <button onclick="showTechnique('grounding')">🌍 Grounding</button>
    </div>
  </div>
</div>
```

---

### 📈 **13.5: Relatórios e Estatísticas**

#### **Gráficos Específicos**

```javascript
// Gráfico de frequência de episódios ao longo do tempo
function renderCompulsionFrequencyChart(entries, days = 30) {
  // Line chart mostrando episódios por dia
  // Meta: tendência de redução ao longo do tempo
}

// Heatmap de gatilhos x horários
function renderTriggerHeatmap(entries) {
  // Mostra quais emoções são mais comuns em cada horário
}

// Efetividade de técnicas (bar chart)
function renderTechniqueEffectivenessChart(entries) {
  // Compara sucesso de cada técnica
}

// Correlação com humor geral
function renderMoodVsCompulsionChart(moods, compulsionEntries) {
  // Mostra se dias com mais compulsão têm humor pior
}
```

---

## 🔧 Implementação Técnica

### **Localização no Código**

1. **Nova Tab:** Adicionar após linha 1095 (após tab Mindfulness)
2. **Schema:** Adicionar após linha 1437
3. **DataStore:** Adicionar object store `foodCompulsion`
4. **Dashboard Cards:** Integrar estatísticas no dashboard principal
5. **Funções:** Adicionar após linha 2523 (após `saveEmotion()`)

### **Integrações**

- ✅ **Com Emoções:** Carregar emoções do dia automaticamente
- ✅ **Com Humor:** Correlacionar humor do dia com episódios
- ✅ **Com Práticas:** Sugerir práticas baseadas em gatilhos
- ✅ **Com Sessões:** Incluir resumo na nota de sessão

### **Analytics**

```javascript
// Eventos a rastrear
trackEvent('compulsao_registrada', {
  emocoes_antes: emotions.length,
  intensidade_antes: intensityBefore,
  usou_tecnica: usedTechnique,
  tecnica_efetiva: techniqueEffectiveness
});

trackEvent('compulsao_evitada', {
  tecnica_usada: technique,
  intensidade_emocao: intensity
});
```

---

## ✅ Checklist de Implementação

### **Fase 1: Estrutura Base** (4h)
- [ ] Criar schema `FoodCompulsionEntry`
- [ ] Adicionar object store no IndexedDB
- [ ] Criar tab `#foodCompulsion`
- [ ] Implementar formulário de registro completo
- [ ] Função `saveFoodCompulsionEntry()`
- [ ] Histórico básico

### **Fase 2: Visualizações** (4h)
- [ ] Dashboard de estatísticas
- [ ] Gráfico de frequência de episódios
- [ ] Top gatilhos e técnicas efetivas
- [ ] Sistema de insights automáticos

### **Fase 3: Plano de Ação** (3h)
- [ ] Card de plano de ação
- [ ] Checagem rápida de emoções
- [ ] Sugestão de técnicas baseada em intensidade
- [ ] Botões de resultado (evitou/registrou)

### **Fase 4: Educação** (2h)
- [ ] Seção educacional (acordeão)
- [ ] Explicação do ciclo da compulsão
- [ ] Lista de alimentos estratégicos
- [ ] Dicas de uso do diário

### **Fase 5: Integrações** (3h)
- [ ] Integrar com registro de emoções
- [ ] Correlacionar com humor do dia
- [ ] Incluir em relatório PDF
- [ ] Analytics completo

### **Fase 6: Polimento** (2h)
- [ ] Responsividade mobile
- [ ] Validação de formulário
- [ ] Notificações de sucesso
- [ ] Testes completos

---

## 📊 Estimativa Total

**⏱️ Tempo Total:** 18 horas

**Complexidade:** 🔴 Alta (módulo completo novo)

**Impacto:** 🔴🔴🔴 **CRÍTICO** (baseado em sessão de terapia real do usuário)

---

## 🎯 Justificativa de Prioridade

1. ✅ **Demanda Real:** Baseado em sessão de terapia do usuário
2. ✅ **Tarefa Terapêutica:** Psicóloga pediu auto-monitoramento
3. ✅ **Diferencial:** Poucos apps DBT têm foco em compulsão alimentar
4. ✅ **Integração:** Complementa funcionalidades existentes (emoções, práticas)
5. ✅ **Valor Terapêutico:** Ferramenta validada cientificamente (DBT)

---

**Recomendação:** Implementar como **Fase 0** (antes das outras melhorias) ou **Fase 1.5** (logo após correções críticas).

O usuário pode começar a usar IMEDIATAMENTE para cumprir a tarefa terapêutica da semana! 🎯
