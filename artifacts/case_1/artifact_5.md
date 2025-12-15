---
title: "Артефакт 5 — Карта зависимостей"
permalink: /artifacts/case_1/artifact_5/
---

# Артефакт 5 — Карта зависимостей

<p class="text-muted mb-3">
Схема “что от чего зависит” для Web/Android/Employee App/Hardware и аналитики.
</p>

<div class="card border mb-4">
  <div class="card-body">
    <div class="ratio ratio-16x9">
      <svg viewBox="0 0 1200 675" width="100%" height="100%" role="img" aria-label="Карта зависимостей">
        <defs>
          <style>
            .node { fill:#fff; stroke:#d7dee7; stroke-width:2; }
            .title { font: 20px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill:#0f172a; font-weight:700; }
            .text  { font: 15px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill:#475569; }
            .arrow { stroke:#94a3b8; stroke-width:2.5; fill:none; marker-end:url(#arrowhead); }
            .arrow2{ stroke:#94a3b8; stroke-width:2.5; fill:none; marker-end:url(#arrowhead); marker-start:url(#arrowheadStart); }
          </style>

          <marker id="arrowhead" markerWidth="10" markerHeight="10" refX="9" refY="5" orient="auto">
            <path d="M0,0 L10,5 L0,10 Z" fill="#94a3b8"></path>
          </marker>
          <marker id="arrowheadStart" markerWidth="10" markerHeight="10" refX="1" refY="5" orient="auto">
            <path d="M10,0 L0,5 L10,10 Z" fill="#94a3b8"></path>
          </marker>
        </defs>

        <!-- LEFT COLUMN -->
        <rect class="node" x="60" y="90" rx="16" ry="16" width="330" height="130"></rect>
        <text class="title" x="85" y="130">Web: “Привязка БП”</text>
        <text class="text"  x="85" y="160">• имя БВС + код</text>
        <text class="text"  x="85" y="185">• оффлайн-сценарий</text>
        <text class="text"  x="85" y="210">• история регистраций</text>

        <rect class="node" x="60" y="265" rx="16" ry="16" width="330" height="130"></rect>
        <text class="title" x="85" y="305">Android: “Зарегистрировать/код”</text>
        <text class="text"  x="85" y="335">• генерация/показ/отправка кода</text>
        <text class="text"  x="85" y="360">• поддержка offline</text>

        <!-- MIDDLE COLUMN -->
        <rect class="node" x="435" y="90" rx="16" ry="16" width="330" height="130"></rect>
        <text class="title" x="460" y="130">Справочники</text>
        <text class="text"  x="460" y="160">• поля / техника / сотрудники</text>
        <text class="text"  x="460" y="185">• активность админа</text>

        <rect class="node" x="435" y="265" rx="16" ry="16" width="330" height="160"></rect>
        <text class="title" x="460" y="305">Качество данных операций</text>
        <text class="text"  x="460" y="335">• тип / дата / время</text>
        <text class="text"  x="460" y="360">• GPS / идентификация</text>
        <text class="text"  x="460" y="385">• чеки / корректные связи</text>

        <rect class="node" x="435" y="470" rx="16" ry="16" width="330" height="115"></rect>
        <text class="title" x="460" y="510">Hardware/правила</text>
        <text class="text"  x="460" y="540">• антенны/реле</text>
        <text class="text"  x="460" y="565">• “ближайшее ТС” / ручной режим</text>

        <!-- RIGHT COLUMN -->
        <rect class="node" x="810" y="90" rx="16" ry="16" width="330" height="130"></rect>
        <text class="title" x="835" y="130">Отчёты / рейтинг / статистика</text>
        <text class="text"  x="835" y="160">• зависят от справочников</text>
        <text class="text"  x="835" y="185">• и качества операций</text>

        <rect class="node" x="810" y="265" rx="16" ry="16" width="330" height="130"></rect>
        <text class="title" x="835" y="305">Employee App</text>
        <text class="text"  x="835" y="335">• учётки сотрудников</text>
        <text class="text"  x="835" y="360">• API чеков/календаря</text>

        <rect class="node" x="810" y="470" rx="16" ry="16" width="330" height="115"></rect>
        <text class="title" x="835" y="510">“Свой-Чужой”</text>
        <text class="text"  x="835" y="540">• RFID + реле блокировки</text>

        <!-- ARROWS (clean, non-crossing) -->
        <!-- Web <-> Android -->
        <path class="arrow2" d="M225,225 L225,265"></path>

        <!-- Web -> Справочники -->
        <path class="arrow" d="M390,155 L435,155"></path>

        <!-- Android -> Качество данных -->
        <path class="arrow" d="M390,330 L435,330"></path>

        <!-- Справочники -> Отчёты -->
        <path class="arrow" d="M765,155 L810,155"></path>

        <!-- Качество данных -> Отчёты -->
        <path class="arrow" d="M765,345 L810,185"></path>

        <!-- Справочники -> Employee App -->
        <path class="arrow" d="M765,155 L810,295"></path>

        <!-- Hardware/правила -> Свой-Чужой -->
        <path class="arrow" d="M765,525 L810,525"></path>
      </svg>
    </div>

     <h2 class="h5 mb-3">Зависимости (текстом)</h2>

    <div class="row g-3">
      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Привязка БП: Web ⇄ Android</h3>
            <ul class="mb-0">
              <li><b>Web “Привязка БП” ⇄ Android “Зарегистрировать/код”</b></li>
              <li>Имя БВС + код</li>
              <li>Оффлайн-сценарий</li>
              <li>История регистраций</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Отчёты / рейтинг / статистика</h3>
            <ul class="mb-0">
              <li>Зависят от <b>заполненных справочников</b> (поля/техника/сотрудники)</li>
              <li>И от <b>корректных данных операций</b> (тип/дата/время/GPS/идентификация)</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">Employee App</h3>
            <ul class="mb-0">
              <li>Зависит от наличия <b>учёток сотрудников</b> (логин/пароль)</li>
              <li>И от <b>API выдачи чеков/календаря</b></li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card border h-100">
          <div class="card-body">
            <h3 class="h6">“Свой-Чужой”</h3>
            <ul class="mb-0">
              <li>Зависит от монтажа <b>RFID-антенн</b> и <b>реле блокировки шнека</b></li>
              <li>И от правил: <b>“ближайшее ТС” / ручной режим</b></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</div>

<div class="alert alert-light border mb-0">
  <strong>Пояснение:</strong>
  регистрация БП — это связка <em>Web ↔ Android</em>; аналитика (отчёты/статистика) появляется только при заполненных справочниках и корректных операциях.
</div>
