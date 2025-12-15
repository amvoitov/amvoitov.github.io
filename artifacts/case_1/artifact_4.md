---
title: "Артефакт 4 — Roadmap продукта (компоненты системы)"
permalink: /artifacts/case_1/artifact_4/
---

<div class="d-flex flex-wrap justify-content-between align-items-center gap-2 mb-3">
  <a class="btn btn-outline-secondary btn-sm" href="{{ '/artifacts/case_1/' | relative_url }}">← К артефактам кейса</a>
  <a class="btn btn-outline-primary btn-sm" href="{{ '/projects/case_1/' | relative_url }}">К кейсу</a>
</div>

<div class="card shadow-sm">
  <div class="card-body p-4">

    <div class="d-flex flex-wrap align-items-center justify-content-between gap-2 mb-2">
      <h1 class="h3 mb-0">Roadmap продукта: компоненты системы</h1>
      <span class="badge text-bg-light border">ТЗ Web-Automation</span>
    </div>

    <p class="text-secondary mb-4">
      Компоненты и зоны ответственности: от планшета на технике до веб-кабинета, приложения сотрудника и backend/данных.
    </p>

    <h2 class="h5 mb-3">Схема компонентов</h2>

    <div class="card border mb-4">
      <div class="card-body">
        <div class="ratio ratio-21x9">
          <svg viewBox="0 0 1200 520" width="100%" height="100%" role="img" aria-label="Схема компонентов системы">
            <defs>
              <style>
                .b { fill: #ffffff; stroke: #cfd6df; stroke-width: 2; }
                .t { font: 18px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill: #0f172a; }
                .s { font: 14px system-ui, -apple-system, Segoe UI, Roboto, Arial; fill: #475569; }
                .a { stroke: #94a3b8; stroke-width: 3; fill: none; marker-end: url(#arrow); }
              </style>
              <marker id="arrow" markerWidth="12" markerHeight="12" refX="10" refY="6" orient="auto">
                <path d="M0,0 L12,6 L0,12 z" fill="#94a3b8"></path>
              </marker>
            </defs>

            <!-- Boxes -->
            <rect class="b" x="40"  y="60"  rx="14" ry="14" width="320" height="130"></rect>
            <text class="t" x="60" y="98">Hardware / Интеграции</text>
            <text class="s" x="60" y="128">RFID-антенны</text>
            <text class="s" x="60" y="152">Блокировка шнека (реле Wi-Fi)</text>
            <text class="s" x="60" y="176">COM-оборудование партнёров</text>

            <rect class="b" x="40"  y="240" rx="14" ry="14" width="320" height="180"></rect>
            <text class="t" x="60" y="278">Android (планшет)</text>
            <text class="s" x="60" y="308">Вес/режимы • операции/чеки</text>
            <text class="s" x="60" y="332">Печать • offline-очередь</text>
            <text class="s" x="60" y="356">Протокол обмена</text>
            <text class="s" x="60" y="380">Инженерка/калибровка</text>
            <text class="s" x="60" y="404">RFID / “Свой-Чужой”</text>

            <rect class="b" x="440" y="170" rx="14" ry="14" width="320" height="170"></rect>
            <text class="t" x="460" y="208">Backend / Данные</text>
            <text class="s" x="460" y="238">Хранение транзакций</text>
            <text class="s" x="460" y="262">Правила доступа</text>
            <text class="s" x="460" y="286">“Непривязанные” 3–6 месяцев</text>
            <text class="s" x="460" y="310">Приём телеметрии/операций</text>
            <text class="s" x="460" y="334">Отчёты / статистика</text>

            <rect class="b" x="840" y="60"  rx="14" ry="14" width="320" height="200"></rect>
            <text class="t" x="860" y="98">Web (ЛК + админка)</text>
            <text class="s" x="860" y="128">Регистрация • роли</text>
            <text class="s" x="860" y="152">Карта + календарь</text>
            <text class="s" x="860" y="176">Поля/техника/сотрудники</text>
            <text class="s" x="860" y="200">Рейтинг • отчёты</text>
            <text class="s" x="860" y="224">“Сообщить о проблеме”</text>
            <text class="s" x="860" y="248">Привязка БП к аккаунту</text>

            <rect class="b" x="840" y="300" rx="14" ry="14" width="320" height="120"></rect>
            <text class="t" x="860" y="338">Employee App (Android/iOS)</text>
            <text class="s" x="860" y="368">Электронные чеки + календарь</text>
            <text class="s" x="860" y="392">Орг/логин/пароль + 6-значный код</text>

            <!-- Arrows -->
            <path class="a" d="M360,125 C410,125 410,125 440,220"></path>
            <path class="a" d="M360,330 C410,330 410,300 440,255"></path>
            <path class="a" d="M760,240 C800,240 820,200 840,160"></path>
            <path class="a" d="M760,270 C800,270 820,320 840,350"></path>
          </svg>
        </div>
      </div>
    </div>

    <h2 class="h5 mb-3">Компоненты системы</h2>

    <div class="row g-3">

      <div class="col-12 col-lg-6">
        <div class="card h-100 border">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <h3 class="h6 mb-0">Android (планшет в тракторе)</h3>
              <span class="badge text-bg-light border">On-field</span>
            </div>
            <ul class="mb-0">
              <li>вес / режимы</li>
              <li>операции / чеки</li>
              <li>печать</li>
              <li>оффлайн-очередь</li>
              <li>протокол обмена</li>
              <li>инженерное меню / калибровка</li>
              <li>RFID / “Свой-Чужой”</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card h-100 border">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <h3 class="h6 mb-0">Web (ЛК хозяйства + системная админка)</h3>
              <span class="badge text-bg-light border">B2B</span>
            </div>
            <ul class="mb-0">
              <li>регистрация / роли</li>
              <li>карта + календарь</li>
              <li>поля / техника / сотрудники</li>
              <li>рейтинг</li>
              <li>статистика / отчёты</li>
              <li>“сообщить о проблеме”</li>
              <li>привязка БП к аккаунту</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card h-100 border">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <h3 class="h6 mb-0">Employee App (Android/iOS)</h3>
              <span class="badge text-bg-light border">Employees</span>
            </div>
            <ul class="mb-0">
              <li>электронные чеки + календарь</li>
              <li>онлайн-доступ</li>
              <li>регистрация: организация/логин/пароль</li>
              <li>подтверждение: 6-значный код</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12 col-lg-6">
        <div class="card h-100 border">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <h3 class="h6 mb-0">Backend / Данные</h3>
              <span class="badge text-bg-light border">Core</span>
            </div>
            <ul class="mb-0">
              <li>хранение транзакций</li>
              <li>правила доступа</li>
              <li>хранение “непривязанных” данных: 3–6 месяцев</li>
              <li>приём телеметрии / операций</li>
              <li>отчёты / статистика</li>
            </ul>
          </div>
        </div>
      </div>

      <div class="col-12">
        <div class="card border">
          <div class="card-body">
            <div class="d-flex align-items-center justify-content-between gap-2 mb-2">
              <h3 class="h6 mb-0">Hardware / Интеграции</h3>
              <span class="badge text-bg-light border">Periphery</span>
            </div>
            <ul class="mb-0">
              <li>RFID-антенны</li>
              <li>устройство блокировки шнека (реле Wi-Fi с аварийным отключением)</li>
              <li>COM-оборудование партнёров</li>
            </ul>
          </div>
        </div>
      </div>

    </div>

  </div>
</div>
